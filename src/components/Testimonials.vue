<template>
    <section class="bg-slate-50 manrope py-16 px-6 font-sans">
        <div class="max-w-7xl mx-auto">
            <div class="text-center mb-16">
                <span
                    class="text-[#FC770A] text-sm font-bold uppercase tracking-[0.5em]"
                    >Avis Clients</span
                >
                <h2 class="text-4xl md:text-5xl font-black text-slate-900 mt-2">
                    L'Excellence Reconnue
                </h2>
            </div>

            <div class="grid md:grid-cols-3 gap-8">
                <div
                    v-for="(avis, index) in testimonials"
                    :key="index"
                    class="bg-white p-8  shadow-sm relative border-b-4 transition-transform hover:-translate-y-2"
                    :class="
                        index === 1 ? 'border-[#023A82]' : 'border-[#FC770A]'
                    "
                >
                    <div class="absolute top-6 right-8 text-blue-100">
                        <Quote
                            size="48"
                            fill="currentColor"
                            class="opacity-50"
                        />
                    </div>

                    <div class="flex gap-1 mb-6">
                        <Star
                            v-for="i in 5"
                            :key="i"
                            size="14"
                            class="fill-[#FC770A] text-[#FC770A]"
                        />
                    </div>

                    <p
                        class="text-gray-500 italic leading-relaxed mb-8 relative z-10"
                    >
                        "{{ avis.text }}"
                    </p>

                    <div class="flex justify-between    items-center">
                        <span class="font-bold text-slate-800">{{
                            avis.author
                        }}</span>
                        <span class="text-sm text-gray-400">{{
                            new Date(avis.date).toLocaleDateString("fr-FR", {
                                year: "numeric",
                                month: "long",
                                day: "numeric",
                            })
                        }}</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { Star, Quote } from "@lucide/vue";

const testimonials = [
    {
        author: "Jérémy F.",
        date: "2025-12-02",
        text: "Installation d'une climatisation réversible dans nos bureaux, rès bon conseil sur le choix du matériel pour optimiser la consommation d'énergie",
    },
    {
        author: "Adem R.",
        date: "2026-01-17",
        text: "Une fuite d'ea importante ",
    },
    {
        author: "Cynthia M.",
        date: "2026-03-25",

        text: "J'ai fait appel à cette entreprise pour le remplacement complet de ma vieille chaudière par une pompe à chaleur. Travail soigné, explications claires sur le fonctionnement et surtout, un chantier laissé impeccable. Je recommande vivement pour leur professionnalisme.",
    },
];
</script>
