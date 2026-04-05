<template>
    <section class="bg-white py-16 manrope px-6 md:px-12 max-w-7xl mx-auto">
        <div class="grid md:grid-cols-2 gap-16">
            <div class="space-y-8">
                <div>
                    <h2 class="text-3xl font-bold mb-4">Parlons de votre projet</h2>
                    <div class="w-16 h-1 bg-[#FC770A] mb-6"></div>
                    <p class="">
                        Nos techniciens sont à votre écoute pour toute demande d'intervention ou de devis personnalisé.
                    </p>
                </div>

                <div class="space-y-6 pt-4">
                    <div class="flex items-start gap-4">
                        <div class="bg-[#023A81]/10 p-3 rounded text-[#023A81]">
                            <MapPin size="24" />
                        </div>
                        <div>
                            <h4 class="font-bold text-slate-900">Notre Siège</h4>
                            <p class="text-gray-500">42100 Saint-Étienne</p>
                        </div>
                    </div>

                    <div class="flex items-start gap-4">
                        <div class="bg-[#023A81]/10 p-3 rounded text-[#023A81]">
                            <Phone size="24" />
                        </div>
                        <div>
                            <h4 class="font-bold text-slate-900">Téléphone</h4>
                            <p class="text-gray-500 text-sm md:text-base">07 65 50 88 33</p>
                        </div>
                    </div>

                    <div class="flex items-start gap-4">
                        <div class="bg-[#023A81]/10 p-3 rounded text-[#023A81]">
                            <Mail size="24" />
                        </div>
                        <div>
                            <h4 class="font-bold text-slate-900">Email</h4>
                            <p class="text-gray-500">yellies-megdiche1@hotmail.fr</p>
                        </div>
                    </div>
                </div>
            </div>

            <form ref="formRef" @submit.prevent="sendEmail" class="space-y-6 bg-white p-2">
                <div class="grid md:grid-cols-2 gap-4">
                    <div class="flex flex-col">
                        <label class="text-sm font-bold mb-2">Nom complet</label>
                        <input
                            v-model="formData.user_name"
                            name="user_name"
                            type="text"
                            required
                            placeholder="John Doe"
                            class="w-full p-4 bg-white border border-gray-100 rounded-md shadow-sm outline-none transition focus:border-[#023A82]"
                        />
                    </div>

                    <div class="flex flex-col">
                        <label class="text-sm font-bold mb-2">mail</label>
                        <input
                            v-model="formData.user_email"
                            name="user_email"
                            type="email"
                            required
                            placeholder="john@doe.com"
                            class="w-full p-4 bg-white border border-gray-100 rounded-md shadow-sm outline-none transition focus:border-[#023A82]"
                        />
                    </div>
                </div>

                <div class="flex flex-col">
                    <label class="text-sm font-bold mb-2">Type de service</label>
                    <div class="relative w-full">
                        <select
                            v-model="formData.service_type"
                            name="service_type"
                            required
                            class="my-2 w-full p-4 bg-white border border-gray-100 rounded-md shadow-sm appearance-none outline-none pr-10 focus:border-[#023A82]"
                        >
                            <option value="">Choisissez un service</option>
                            <option value="plomberie">Plomberie</option>
                            <option value="chauffage">Chauffage</option>
                            <option value="climatisation">Climatisation</option>
                        </select>
                        <div class="absolute inset-y-0 right-3 flex items-center pointer-events-none">
                            <ChevronDown size="20" class="text-gray-500" />
                        </div>
                    </div>
                </div>

                <div class="flex flex-col">
                    <label class="text-sm font-bold mb-2">Message</label>
                    <textarea
                        v-model="formData.message"
                        name="message"
                        rows="4"
                        required
                        placeholder="Décrivez votre besoin..."
                        class="w-full p-4 bg-white border border-gray-100 rounded-md shadow-sm outline-none transition focus:border-[#023A82]"
                    ></textarea>
                </div>

                <button
                    type="submit"
                    :disabled="loading"
                    class="w-full bg-[#023A82] text-white font-bold py-4 rounded-md shadow-lg hover:bg-blue-900 flex justify-center items-center gap-2 transition-all active:scale-95 disabled:opacity-50 disabled:cursor-not-allowed"
                >
                    {{ loading ? 'Envoi en cours...' : 'Envoyer ma demande' }}
                    <Send size="20" class="rotate-[-10deg]" />
                </button>
            </form>
        </div>
    </section>

    <div class="fixed bottom-8 right-10">
        <a href="#accueil" class="bg-[#FC770A] text-white p-3 hover:scale-105 rounded-full shadow-lg transition flex items-center justify-center">
            <ArrowUp size="20" stroke-width="2.5" />
        </a>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import { MapPin, Phone, Mail, Send, ArrowUp, ChevronDown } from "@lucide/vue";
import emailjs from '@emailjs/browser';

// Référence pour le formulaire HTML
const formRef = ref(null);
const loading = ref(false);

// Données réactives pour v-model
const formData = ref({
    user_name: '',
    user_email: '',
    service_type: '',
    message: ''
});

const sendEmail = () => {
    loading.value = true;

    // REMPLACE CES VALEURS PAR TES IDS EMAILJS
    const serviceID = 'service_r9e95gl';
    const templateID = 'template_ufc457k';
    const publicKey = 'znf42iPkAieid0EQY';

    emailjs.sendForm(serviceID, templateID, formRef.value, publicKey)
        .then(() => {
            alert('Demande envoyée avec succès !');
            // Reset du formulaire
            formData.value = { user_name: '', user_email: '', service_type: '', message: '' };
        })
        .catch((error) => {
            alert("Erreur lors de l'envoi : " + error.text);
        })
        .finally(() => {
            loading.value = false;
        });
};
</script>

<style scoped>
/* Supprime la mention EmailJS dans l'email envoyé */
:deep(.emailjs-branding) {
    display: none !important;
    visibility: hidden !important;
    opacity: 0 !important;
    height: 0 !important;
    width: 0 !important;
    font-size: 0 !important;
}
</style>

<!-- yellies-megdiche1@hotmail.fr -->