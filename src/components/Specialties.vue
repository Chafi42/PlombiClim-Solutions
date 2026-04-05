<template>
    <section class="py-16 px-6 manrope max-w-7xl mx-auto">
        <h2 class="text-3xl font-black text-slate-900 mb-4">Nos Spécialités</h2>
        <div class="w-16 h-1 bg-[#FC770A] mb-6"></div>
        <div class="grid md:grid-cols-3 translate-y-4 gap-6">
            <div
              v-for="(spec, index) in specialties"
              :key="spec.title"
              class="p-8 bg-white hover:-translate-y-2 shadow-sm border-b-4 transition-all"
              :class="index % 3 === 1 ? 'border-[#FC770A]' : 'border-[#023A82]'"
            >
              <component
                :is="spec.icon"
                class="w-12 h-12 mb-4 p-3 rounded"
                stroke-width="2"
                :class="{
                  'text-[#023A82] bg-[#023A82]/10' : index % 3 !== 1,
                  'text-[#FC770A] bg-[#FC770A]/10': index % 3 === 1,
                  
                }"
              />
              <h3 class="text-xl mb-4">{{ spec.title }}</h3>
              <p class="text-sm leading-relaxed">
                {{ spec.desc }}
              </p>
            </div>
        </div>
    </section>
</template>

<script setup>
import { Droplets, Flame, Wind } from "@lucide/vue";

const specialties = [
    {
        title: "Plomberie",
        icon: Droplets,
        desc: "On s’occupe de tout : de la pose de vos canalisations à la création de votre salle de bain de luxe, sans oublier la détection de fuites avec du matériel de précision.",
    },
    {
        title: "Chauffage",
        icon: Flame,
        desc: "Pompes à chaleur, chaudières gaz haute performance ou chauffage au sol : profitez d'une chaleur parfaite partout, sans faire l'impasse sur les économies.",
    },
    {
        title: "Climatisation",
        icon: Wind,
        desc: "On vous installe une clim discrète ou classique qui fait aussi chauffage, qui purifie votre air et qui ne plombe pas votre facture d'électricité.",
    },
];
</script>
