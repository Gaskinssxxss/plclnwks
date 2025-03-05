<template>
    <div id="emergency-section" class="flex flex-col 2xl:flex-row justify-between py-6 space-x-2">
        <div class="pl-4">
            <div class="font-anton uppercase text-4xl md:text-7xl">
                <h1>Declare your emergency to us. Fill all the form, <span class="text-che bg-black px-4">see and
                        wait!</span></h1>
            </div>
        </div>
        <div class="border-2 border-black p-4 font-anton uppercase max-w-xl bg-white text-black mt-6 2xl:mt-0">
            <div class="text-3xl md:text-4xl">
                <h1 class="text-che bg-black p-2">
                    I'm Declaring Emergency!
                </h1>
            </div>
            <div class="py-4">
                <div>
                    <table class="border border-black w-full table-fixed">
                        <tbody class="grid grid-cols-2 md:grid-cols-3">
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6 accent-black" type="checkbox" v-model="bigData">
                                    <span class="mx-2">Big Data</span>
                                </td>
                            </tr>
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6 accent-black" type="checkbox" v-model="ai">
                                    <span class="mx-2">AI</span>
                                </td>
                            </tr>
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6 accent-black" type="checkbox" v-model="cloudBackup">
                                    <span class="mx-2">Backup System</span>
                                </td>
                            </tr>
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6 accent-black" type="checkbox" v-model="cloudArchive">
                                    <span class="mx-2">Archiving System</span>
                                </td>
                            </tr>
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6 accent-black" type="checkbox" v-model="security">
                                    <span class="mx-2">Cyber Security</span>
                                </td>
                            </tr>
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6 accent-black" type="checkbox" v-model="web">
                                    <span class="mx-2">Web Dev</span>
                                </td>
                            </tr>
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6" type="checkbox" v-model="mobile">
                                    <span class="mx-2">Mobile Dev</span>
                                </td>
                            </tr>
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6" type="checkbox" v-model="sys">
                                    <span class="mx-2">Sys Analyst</span>
                                </td>
                            </tr>
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6" type="checkbox" v-model="datas">
                                    <span class="mx-2">Data Analyst</span>
                                </td>
                            </tr>
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6" type="checkbox" v-model="robot">
                                    <span class="mx-2">Robotics</span>
                                </td>
                            </tr>
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6" type="checkbox" v-model="iot">
                                    <span class="mx-2">Internet of Things</span>
                                </td>
                            </tr>
                            <tr class="w-full">
                                <td class="border border-black p-2 flex items-center w-full">
                                    <input class="w-6 h-6" type="checkbox" v-model="election">
                                    <span class="mx-2">Election Survey</span>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                <div class="pt-6">
                    <table class="border-2 border-black w-full table-fixed">
                        <tbody>
                            <tr>
                                <td class="border-2 border-black pl-4 w-1/3">Business Name</td>
                                <td class="border border-black">
                                    <input class="pl-2 py-2 w-full min-w-[200px] bg-white text-black" type="text"
                                        v-model="business">
                                </td>
                            </tr>
                            <tr>
                                <td class="border-2 border-black pl-4 w-1/3">Country</td>
                                <td class="border border-black">
                                    <input class="pl-2 py-2 w-full min-w-[200px] bg-white text-black" type="text"
                                        v-model="country">
                                </td>
                            </tr>
                            <tr>
                                <td class="border-2 border-black pl-4 w-1/3">Full Name</td>
                                <td class="border border-black">
                                    <input class="pl-2 py-2 w-full min-w-[200px] bg-white text-black" type="text"
                                        v-model="name">
                                </td>
                            </tr>
                            <tr>
                                <td class="border-2 border-black pl-4 w-1/3">Email</td>
                                <td class="border border-black">
                                    <input class="pl-2 py-2 w-full min-w-[200px] bg-white text-black" type="email"
                                        v-model="email">
                                </td>
                            </tr>
                            <tr>
                                <td class="border-2 border-black pl-4 w-1/3">Tell Us</td>
                                <td class="border border-black">
                                    <textarea
                                        class="pl-2 w-full min-w-[200px] h-24 bg-white text-black pb-2 text-xs tracking-wider"
                                        v-model="contain"></textarea>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
            <div>
                <div class="flex flex-col md:flex-row space-y-4 md:space-y-0 md:space-x-4 pt-4">
                    <div class="flex items-start">
                        <input class="w-6 sm:w-10 h-6 sm:h-10" type="checkbox" v-model="check">
                        <h1 class="text-xs md:text-sm mx-2">I consent to my data being used for the purposes of the
                            Declaration, and to my name and reason being used to Cooperate on declarations on this site
                            and throughout product submissions.</h1>
                    </div>
                </div>
            </div>
            <div class="pt-4 flex justify-end text-3xl">
                <button class="bg-black rounded-lg" @click="sendEmail">
                    <div
                        class="text-start text-black bg-che transition-transform duration-300 ease-linear transform -translate-x-1 -translate-y-1 hover:-translate-x-0 hover:-translate-y-0 rounded-lg border-2 border-black p-2">
                        <h1>
                            Declare
                        </h1>
                    </div>
                </button>
            </div>
        </div>
    </div>
</template>

<script>
import emailjs from "emailjs-com";

export default {
    data() {
        return {
            bigData: false,
            ai: false,
            cloudBackup: false,
            cloudArchive: false,
            security: false,
            web: false,
            mobile: false,
            sys: false,
            datas: false,
            iot: false,
            robot: false,
            ddd: false,
            election: false,
            business: '',
            country: '',
            name: '',
            email: '',
            contain: '',
            check: null
        }
    },
    methods: {
        sendEmail() {
            if (!this.business || !this.country || !this.name || !this.email || !this.contain || !this.check) {
                alert("Please fill all the required fields.");
                return;
            }

            if (!this.bigData && !this.ai && !this.cloudArchive && !this.cloudBackup && !this.security && !this.web && !this.mobile && !this.sys && !this.datas && !this.iot) {
                alert("Please select at least one service option.");
                return;
            }

            const serviceID = "service_guvuew3";
            const templateID = "template_pti5o9k";

            const templateParams = {
                business: this.business,
                country: this.country,
                name: this.name,
                email: this.email,
                contain: this.contain,
                bigData: this.bigData,
                ai: this.ai,
                cloudBackup: this.cloudBackup,
                cloudArchive: this.cloudArchive,
                security: this.security,
                web: this.web,
                mobile: this.mobile,
                sys: this.sys,
                datas: this.datas,
                iot: this.iot,
                robot: this.robot,
                ddd: this.ddd,
                election: this.election
            };

            emailjs.send(serviceID, templateID, templateParams, "-DEFQdHYri_Q8uiHg")
                .then(response => {
                    alert("Email successfully sent!");
                    console.log(response)
                    window.location.reload()
                })
                .catch(error => {
                    alert("Please Check the Field. Please try again.");
                    console.log(error);
                });
        }
    },
}
</script>

<style>
input[type="checkbox"] {
    accent-color: black;
}

input[type="checkbox"]:checked {
    accent-color: #B20600;
}
</style>


<!-- <template>
    <div id="emergency-section" class="flex justify-between py-6">
        <div class="pl-4">
            <div class="font-anton uppercase text-7xl">
                <h1>Declare ur emergency to us. Fill all the form, see n waiting!</h1>
            </div>
        </div>
        <div class="border-2 border-gray-300 p-4 font-anton uppercase max-w-xl bg-white text-gray-300">
            <div class="text-4xl">
                <h1 class="text-che">
                    I'm Decalring Emergency!
                </h1>
            </div>
            <div class="flex space-x-4 py-6">
                <div>
                    <table class="border-collapse border border-black w-full">
                        <tbody>
                            <tr>
                                <td class="border border-gray-300 p-2 flex items-center">
                                    <input class="w-6 h-6  accent-black" type="checkbox" required v-model="web">
                                    <span class="mx-2 ">Web Development</span>
                                </td>
                            </tr>
                            <tr>
                                <td class="border border-gray-300 p-2 flex items-center">
                                    <input class="w-6 h-6" type="checkbox" required v-model="mobile">
                                    <span class="mx-2">Mobile Development</span>
                                </td>
                            </tr>
                            <tr>
                                <td class="border border-gray-300 p-2 flex items-center">
                                    <input class="w-6 h-6" type="checkbox" required v-model="sys">
                                    <span class="mx-2">Sys Analyst</span>
                                </td>
                            </tr>
                            <tr>
                                <td class="border border-gray-300 p-2 flex items-center">
                                    <input class="w-6 h-6" type="checkbox" required v-model="datas">
                                    <span class="mx-2">Data Analyst</span>
                                </td>
                            </tr>
                            <tr>
                                <td class="border border-gray-300 p-2 flex items-center">
                                    <input class="w-6 h-6" type="checkbox" required v-model="iot">
                                    <span class="mx-2">Internet of Things</span>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                <div>
                    <table class="border-collapse border border-gray-300 w-full">
                        <tbody>
                            <tr>
                                <td class="border border-gray-300 px-2">Business Name</td>
                                <td class="border border-gray-300">
                                    <input class="pl-2 py-2 w-full bg-black" type="text" required v-model="business">
                                </td>
                            </tr>
                            <tr>
                                <td class="border border-gray-300 px-2">Country</td>
                                <td class="border border-gray-300">
                                    <input class="pl-2 py-2 w-full bg-black" type="text" required v-model="country">
                                </td>
                            </tr>
                            <tr>
                                <td class="border border-gray-300 px-2">Full Name</td>
                                <td class="border border-gray-300">
                                    <input class="pl-2 py-2 w-full bg-black" type="text" required v-model="nama">
                                </td>
                            </tr>
                            <tr>
                                <td class="border border-gray-300 px-2">Email</td>
                                <td class="border border-gray-300">
                                    <input class="pl-2 py-2 w-full bg-black" type="email" required v-model="email">
                                </td>
                            </tr>
                            <tr>
                                <td class="border border-gray-300 px-2">Tell Us</td>
                                <td class="border border-gray-300">
                                    <textarea class="pl-2 w-full h-32 py-1 bg-black pb-2 text-xs tracking-wider"
                                        required v-model="contain"></textarea>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
            <div>
                <div class="flex space-x-4 pt-4">
                    <input class="w-10 h-10" type="checkbox" required v-model="check">
                    <h1 class="text-xs">I consent for my data to be used for the purpose of the Declaration, and for my
                        name and reason for
                        joining to be used in the promotion of the Declaration on this site and across our product.
                    </h1>
                </div>
            </div>
            <div class="py-4 flex justify-end text-3xl">
                <button class="bg-gray-300 rounded-lg" @click="sendEmail">
                    <div
                        class="text-start text-black bg-che transition-transform duration-300 ease-linear transform -translate-x-1 -translate-y-1 hover:-translate-x-0 hover:-translate-y-0 rounded-lg border-2 border-black p-2">
                        <h1>
                            Declare
                        </h1>
                    </div>
                </button>
            </div>
        </div>
    </div>
</template>

<script>
import emailjs from "emailjs-com";

export default {
    data() {
        return {
            web: false,
            mobile: false,
            sys: false,
            datas: false,
            iot: false,
            business: '',
            country: '',
            name: '',
            email: '',
            contain: '',
            check: null
        }
    },
    methods: {
        sendEmail() {
            if (!this.business || !this.country || !this.name || !this.email || !this.contain || !this.check) {
                alert("Please fill all the required fields.");
                return;
            }

            if (!this.web && !this.mobile && !this.sys && !this.datas && !this.iot) {
                alert("Please select at least one service option (Web, Mobile, Sys Analyst, Data Analyst, or IoT).");
                return;
            }

            const serviceID = "service_guvuew3";
            const templateID = "template_pti5o9k";

            const templateParams = {
                business: this.business,
                country: this.country,
                name: this.name,
                email: this.email,
                contain: this.contain,
                web: this.web,
                mobile: this.mobile,
                sys: this.sys,
                datas: this.datas,
                iot: this.iot,
            };

            emailjs.send(serviceID, templateID, templateParams, "-DEFQdHYri_Q8uiHg")
                .then(response => {
                    alert("Email successfully sent!");
                    console.log(response);
                })
                .catch(error => {
                    alert("Failed to send email. Please try again.");
                    console.log(error);
                });
        }
    }

}
</script>

<style>
input[type="checkbox"] {
    accent-color: black;
}

input[type="checkbox"]:checked {
    accent-color: #B20600;
}
</style> -->