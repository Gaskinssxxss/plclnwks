<template>
  <div class="p-6">
    <div class="flex">
      <div
        class="bg-white shadow-xl rounded-xl p-2 mb-6 border border-gray-200"
      >
        <h2 class="text-2xl font-semibold mb-4 text-gray-700">Upload File</h2>
        <input
          type="file"
          @change="onFileChange"
          accept=".pdf,.doc,.docx"
          class="border border-gray-300 rounded-lg p-3 w-full mb-4 text-gray-700 focus:ring-2 focus:ring-blue-500"
        />
        <button
          @click="uploadFile"
          :disabled="!file"
          class="bg-blue-500 text-white p-3 rounded-lg w-full hover:bg-blue-600 focus:outline-none focus:ring-2 focus:ring-blue-500 disabled:bg-gray-400"
        >
          Upload File
        </button>
      </div>
    </div>
    <div>
      <div v-if="file">
        <div
          v-if="file.type === 'application/pdf'"
          class="mt-4 p-6 bg-gray-50 border border-gray-200 rounded-lg shadow-md"
        >
          <embed
            :src="filePreviewUrl"
            type="application/pdf"
            class="w-full h-96 border-none"
          />
        </div>
        <div
          class="border border-gray-200 p-6 bg-gray-50 rounded-lg shadow-md"
          v-else-if="
            file.type === 'application/msword' ||
            file.type ===
              'application/vnd.openxmlformats-officedocument.wordprocessingml.document'
          "
        >
          <div ref="docxPreview" class="docx-preview text-gray-800"></div>
        </div>
      </div>
    </div>

    <div v-if="loading" class="flex justify-center items-center mt-6">
      <div class="loader"></div>
    </div>

    <div
      v-if="analysisResult"
      class="mt-12 grid grid-cols-1 sm:grid-cols-3 md:grid-cols-4 gap-4"
    >
      <div class="bg-white p-6 shadow-lg rounded-lg border border-gray-200">
        <h2 class="text-xl font-semibold text-center mb-4 text-gray-800">
          Full Text Sentiment
        </h2>
        <p class="text-lg font-medium text-gray-800 text-center">
          <span
            :class="getSentimentClass(analysisResult.full_text_sentiment)"
            class="font-bold"
          >
            {{ analysisResult.full_text_sentiment.toUpperCase() }}
          </span>
        </p>
      </div>

      <div
        v-for="(paragraph, index) in analysisResult.paragraphs"
        :key="index"
        class="bg-white p-6 shadow-lg rounded-lg border border-gray-200"
      >
        <h3 class="text-xl font-semibold mb-4 text-gray-800">
          Paragraph {{ paragraph.paragraf_ke }}
          <span
            :class="getSentimentClass(paragraph.paragraf_sentimen)"
            class="ml-2"
          >
            ({{ paragraph.paragraf_sentimen.toUpperCase() }})
          </span>
        </h3>
        <ul class="pl-6 space-y-2">
          <li
            v-for="sentence in paragraph.kalimat_sentimen"
            :key="sentence.kalimat_ke"
            class="text-sm text-gray-700"
          >
            <strong>Sentence {{ sentence.kalimat_ke }}:</strong>
            <span :class="getSentimentClass(sentence.sentimen)">
              {{ sentence.teks }} (Sentiment: {{ sentence.sentimen }})
            </span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import mammoth from "mammoth";

export default {
  data() {
    return {
      file: null,
      loading: false,
      analysisResult: null,
      filePreviewUrl: null,
    };
  },
  methods: {
    onFileChange(event) {
      this.file = event.target.files[0];
      if (this.file) {
        this.createFilePreview(this.file);
      }
    },
    createFilePreview(file) {
      if (file.type === "application/pdf") {
        this.filePreviewUrl = URL.createObjectURL(file);
      } else if (
        file.type === "application/msword" ||
        file.type ===
          "application/vnd.openxmlformats-officedocument.wordprocessingml.document"
      ) {
        this.previewDocx(file);
      } else {
        this.filePreviewUrl = null;
      }
    },
    previewDocx(file) {
      const reader = new FileReader();

      reader.onload = (e) => {
        const arrayBuffer = e.target.result;
        mammoth
          .convertToHtml({ arrayBuffer: arrayBuffer })
          .then((result) => {
            this.$nextTick(() => {
              this.$refs.docxPreview.innerHTML = result.value;

              this.addDocxStyles();
            });
          })
          .catch((err) => {
            console.error("Error previewing docx file:", err);
            this.$refs.docxPreview.innerHTML = "<p>Error reading the file</p>";
          });
      };

      reader.readAsArrayBuffer(file);
    },

    addDocxStyles() {
      const docPreview = this.$refs.docxPreview;
      if (docPreview) {
        docPreview.style.padding = "20px";
        docPreview.style.fontFamily = "Arial, sans-serif";
        docPreview.style.lineHeight = "2.0";
        docPreview.style.fontSize = "14px";
        docPreview.style.color = "#333";

        const headers = docPreview.querySelectorAll("h1, h2, h3, h4, h5, h6");
        headers.forEach((header) => {
          header.style.color = "#1a73e8";
        });

        const paragraphs = docPreview.querySelectorAll("p");
        paragraphs.forEach((p) => {
          p.style.marginBottom = "10px";
        });
      }
    },
    formatFileSize(size) {
      if (size < 1024) return `${size} bytes`;
      else if (size < 1048576) return `${(size / 1024).toFixed(2)} KB`;
      else return `${(size / 1048576).toFixed(2)} MB`;
    },
    async uploadFile() {
      const formData = new FormData();
      formData.append("file", this.file);

      this.loading = true;

      try {
        const response = await axios.post(
          "http://localhost:3000/upload",
          formData,
          {
            headers: {
              "Content-Type": "multipart/form-data",
            },
          }
        );

        if (response.data.status === "success") {
          this.analysisResult = response.data.data;
        } else {
          alert("Error: " + response.data.message);
        }
      } catch (error) {
        console.error("Error uploading file:", error);
        alert("Failed to upload the file or analyze it.");
      } finally {
        this.loading = false;
      }
    },
    getSentimentClass(sentiment) {
      switch (sentiment) {
        case "positif":
          return "text-green-600";
        case "negatif":
          return "text-red-600";
        case "netral":
          return "text-gray-600";
        default:
          return "";
      }
    },
  },
};
</script>

<style scoped>
/* Tailwind CSS loader */
.loader {
  border: 4px solid transparent;
  border-top: 4px solid #3498db;
  border-radius: 50%;
  width: 40px;
  height: 40px;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
