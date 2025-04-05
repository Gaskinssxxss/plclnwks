<template>
  <div>
    <div class="flex">
      <div class="bg-star w-full h-6"></div>
      <div class="bg-che w-full h-6"></div>
      <div class="bg-black w-full h-6"></div>
    </div>
    <div class="flex py-6">
      <div
        class="font-roboto font-extrabold capitalize text-2xl sm:text-3xl md:text-4xl"
      >
        <div class="flex space-x-2">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="size-10 text-black"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="m11.25 11.25.041-.02a.75.75 0 0 1 1.063.852l-.708 2.836a.75.75 0 0 0 1.063.853l.041-.021M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Zm-9-3.75h.008v.008H12V8.25Z"
            />
          </svg>
          <h1>Layanan Kami</h1>
        </div>
      </div>
    </div>

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 sm:gap-6">
      <div
        v-for="(service, index) in services"
        :key="index"
        class="cursor-pointer bg-white p-2 rounded-lg shadow-sm hover:bg-gray-100 border border-gray-300 transition-all duration-300"
        @click="toggle(index)"
      >
        <div class="flex items-center space-x-4">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="size-8 text-black"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="m11.25 11.25.041-.02a.75.75 0 0 1 1.063.852l-.708 2.836a.75.75 0 0 0 1.063.853l.041-.021M21 12a9 9 0 1 1-18 0 9 9 0 0 1 18 0Zm-9-3.75h.008v.008H12V8.25Z"
            />
          </svg>
          <h1 class="text-xl tracking-wider font-roboto font-extrabold">
            {{ service.nama }}
          </h1>
        </div>

        <transition name="fade">
          <div
            v-if="activeIndex === index"
            class="mt-4 font-sans font-semibold text-base text-gray-700 space-y-3"
          >
            <p v-for="(paragraph, i) in service.deskripsi" :key="i">
              {{ paragraph }}
            </p>
          </div>
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeIndex: null,
      services: [
        {
          nama: "Big Data",
          deskripsi: [
            "Big Data memiliki banyak kegunaan yang signifikan dalam berbagai sektor. Pertama, ia memungkinkan analisis prediktif untuk meramalkan tren dan perilaku masa depan, membantu perusahaan dalam pengambilan keputusan yang lebih baik. Kedua, Big Data mendukung analisis pelanggan, sehingga perusahaan dapat memahami preferensi dan kebutuhan pelanggan untuk meningkatkan pengalaman mereka.",
            "Selain itu, Big Data digunakan untuk meningkatkan efisiensi operasional dengan mengidentifikasi area yang dapat dioptimalkan, serta untuk manajemen risiko dengan mendeteksi potensi masalah lebih awal. Dalam pemasaran, Big Data memungkinkan personalisasi dan pengautomatisasian kampanye, sementara di sektor keuangan, ia membantu dalam mendeteksi penipuan. Secara keseluruhan, Big Data memberikan wawasan yang berharga yang dapat meningkatkan kinerja dan daya saing perusahaan.",
          ],
        },
        {
          nama: "Sistem Backup",
          deskripsi: [
            "Sistem Backup adalah solusi penyimpanan data yang memungkinkan pengguna untuk menyimpan salinan data secara online melalui internet, memberikan berbagai manfaat seperti keamanan data melalui enkripsi, aksesibilitas dari berbagai perangkat dan lokasi, serta pemulihan data yang cepat dalam kasus kehilangan.",
            "Selain itu, sistem ini menawarkan skalabilitas yang memudahkan pengguna untuk menambah kapasitas penyimpanan sesuai kebutuhan tanpa investasi besar dalam infrastruktur fisik, serta mengurangi biaya untuk perangkat keras dan pemeliharaan.",
          ],
        },
        {
          nama: "Cyber Security",
          deskripsi: [
            "Cyber Security services adalah model layanan yang menyediakan solusi keamanan siber melalui platform berbasis cloud, memungkinkan organisasi untuk melindungi data dan sistem mereka tanpa harus mengelola infrastruktur keamanan secara internal.",
            "Layanan ini meliputi perlindungan terhadap ancaman siber seperti malware, phishing, dan serangan DDoS, serta pemantauan keamanan secara real-time, akses ke keahlian terbaru, dan efisiensi biaya operasional.",
          ],
        },
        {
          nama: "Sistem Pengarsipan",
          deskripsi: [
            "Sistem Pengarsipan adalah solusi penyimpanan yang memungkinkan organisasi untuk menyimpan, mengelola, dan mengakses dokumen serta data secara online dengan kemudahan aksesibilitas dan kolaborasi real-time.",
            "Selain itu, sistem ini menawarkan penghematan biaya dan peningkatan keamanan data melalui enkripsi dan kontrol akses, serta mendukung efisiensi dan produktivitas organisasi.",
          ],
        },
        {
          nama: "Data Analyst",
          deskripsi: [
            "Data Analyst berperan penting dalam mengolah dan menganalisis data untuk membantu organisasi dalam pengambilan keputusan yang berbasis informasi.",
            "Mereka mengumpulkan, membersihkan, dan menginterpretasi data untuk mengidentifikasi tren dan pola serta menyajikan informasi dalam bentuk visualisasi yang mudah dipahami.",
          ],
        },
        {
          nama: "Internet of Things (IoT)",
          deskripsi: [
            "Internet of Things (IoT) adalah jaringan perangkat fisik yang terhubung ke internet untuk mengumpulkan, bertukar, dan menganalisis data secara otomatis.",
            "IoT digunakan dalam industri, pertanian, kesehatan, dan rumah pintar untuk meningkatkan efisiensi operasional, kenyamanan, dan pengambilan keputusan berbasis data.",
          ],
        },
        {
          nama: "Sistem Analyst",
          deskripsi: [
            "Sistem Analyst menjembatani kebutuhan bisnis dengan solusi TI. Mereka menganalisis, merancang, dan mengimplementasikan sistem informasi untuk mendukung tujuan organisasi.",
            "Mereka juga mengidentifikasi masalah sistem, merekomendasikan perbaikan, serta memberikan pelatihan dan dukungan teknis kepada pengguna.",
          ],
        },
        {
          nama: "Web Development",
          deskripsi: [
            "Web Development adalah proses pembuatan dan pemeliharaan situs web yang mencakup desain antarmuka, pemrograman, dan pengelolaan konten.",
            "Web digunakan untuk menampilkan informasi dan layanan, meningkatkan interaksi pengguna, dan membangun hubungan bisnis yang lebih baik secara online.",
          ],
        },
        {
          nama: "Mobile Development",
          deskripsi: [
            "Mobile Development adalah proses pembuatan aplikasi perangkat lunak untuk smartphone dan tablet yang menyediakan akses cepat ke layanan dan informasi.",
            "Aplikasi ini membantu bisnis meningkatkan keterlibatan pelanggan, transaksi e-commerce, dan menawarkan pengalaman pengguna yang lebih personal.",
          ],
        },
        {
          nama: "Robotics",
          deskripsi: [
            "Robotics mencakup pengembangan dan penerapan sistem robotik untuk otomatisasi tugas dalam industri dan kehidupan sehari-hari.",
            "Robot membantu mengurangi waktu, biaya, dan risiko pekerjaan serta mendukung inovasi teknologi melalui robot cerdas yang dapat belajar dan beradaptasi.",
          ],
        },
        {
          nama: "Election Survey & Tim Management",
          deskripsi: [
            "Election Survey & Tim Management menyediakan layanan survei opini publik, pasar, sosial, karyawan, kesehatan, pendidikan, lingkungan, dan teknologi.",
            "Layanan ini membantu klien memahami opini dan perilaku masyarakat serta memberikan dukungan strategis berdasarkan data yang akurat dan mendalam.",
          ],
        },
        {
          nama: "Artificial Intelligence (Object Detection & Classification)",
          deskripsi: [
            "Artificial Intelligence (AI) digunakan untuk mendeteksi dan mengklasifikasikan objek dalam gambar atau video, seperti pengawasan keamanan dan kendaraan otonom.",
            "Teknologi ini juga diterapkan dalam sektor kesehatan, ritel, dan pertanian untuk meningkatkan efisiensi dan akurasi pengambilan keputusan berbasis data visual.",
          ],
        },
      ],
    };
  },
  methods: {
    toggle(index) {
      this.activeIndex = this.activeIndex === index ? null : index;
    },
  },
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
