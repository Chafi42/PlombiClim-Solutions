<template>
  <section class="py-16 manrope px-6 max-w-7xl mx-auto font-sans">
    
    <div class="flex flex-col md:flex-row md:items-end justify-between mb-12 gap-8">
      <div class="max-w-2xl">
        <h2 class="text-3xl font-black text-slate-900 mb-4">Nos Services</h2>
        <div class="w-16 h-1 bg-[#FC770A] mb-6"></div>
      </div>
      
      <div class="inline-flex items-center gap-2 bg-[#023A82]/10 px-4 py-2 rounded-full">
        <div class="w-2 h-2 rounded-full bg-[#021A82]"></div>
        <span class="text-[#021A82] text-sm font-bold">Garanti 10 ans</span>
      </div>
    </div>

    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div v-for="(service, index) in services" :key="index" 
        class="bg-white p-8 shadow-[0_10px_30px_rgba(0,0,0,0.05)] flex flex-col items-start border-b-4 transition-all hover:-translate-y-2 shadow-sm group"
        :class="index % 2 === 0 ? 'border-[#FC770A]' : 'border-[#023A82]'"
      >
        <div class="mb-6 p-3 rounded-lg transition-colors" 
          :class="index % 2 === 0 ? 'text-[#FC770A] bg-orange-50' : 'text-[#023A82] bg-[#023A82]/10'"
        >
          <component :is="service.icon" size="28" stroke-width="2" />
        </div>

        <h3 class="text-xl mb-4">{{ service.title }}</h3>

        <p class="text-sm leading-relaxed mb-4">
          {{ service.desc }}
        </p>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Wrench, Settings, Hammer, ShieldCheck } from '@lucide/vue';

const services = [
  {
    title: 'Rénovation',
    icon: Hammer,
    desc: 'Rénover pour économiser : on améliore vos anciens systèmes pour les rendre plus performants.'
  },
  {
    title: 'Installation',
    icon: Settings,
    desc: 'On vous pose du matériel tout neuf, certifié A+++, pour que vous fassiez un maximum d’économies d’énergie dès le premier jour.'
  },
  {
    title: 'Dépannage',
    icon: Wrench,
    desc: 'Intervention prioritaire en moins de 2h pour vos fuites et pannes critiques.'
  },
  {
    title: 'Entretien',
    icon: ShieldCheck,
    desc: 'Contrats annuels pour assurer la pérennité de vos installations.'
  }
];
</script>