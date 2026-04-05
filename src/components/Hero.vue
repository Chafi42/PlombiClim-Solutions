<template>
    <section  class="relative bg-white manrope overflow-hidden">
        <div id="background"
            class="mx-auto px-6 md:px-16 pt-12 pb-24 flex flex-col md:flex-row items-center gap-12"
        >
            <div class="md:w-1/2 space-y-8 mx-auto max-w-2xl relative z-10">
                <div>
                    <span
                        class="text-[#FC770A] font-bold text-sm uppercase tracking-[0.5em]"
                        >Expertise Certifiée</span
                    >
                    <h1
                        class="text-5xl md:text-6xl font-bold text-slate-900 mt-4 leading-[1.1]"
                    >
                        Plomberie,<br />
                        Chauffage,<br />
                        <span class="text-[#021A82]">Climatisation.</span>
                    </h1>
                </div>

                <p class="max-w-lg">
                    Profitez d'un confort total chez vous grâce à nos
                    installations. On s'occupe de votre chauffage, de votre clim
                    et de votre plomberie avec des solutions fiables,
                    éco-responsables et rapides au poil.
                </p>

                <div class="flex flex-wrap gap-4 pt-4">
                    <a
                        href="#contact"
                        @click="isMenuOpen = false"
                        class="bg-[#FC770A] text-white px-10 py-4 rounded-md font-bold shadow-xl flex items-center gap-2 hover:scale-105 transition-transform"
                    >
                        Parlons-en
                    </a>

                    <a
                        href="#services"
                        @click="isMenuOpen = false"
                        class="bg-gray-300 text-[#021A82] px-10 py-4 rounded-md font-bold border border-[#023A82]/10 hover:bg-[#023A82]/10 transition"
                    >
                        Découvrer nos services
                    </a>
                </div>
            </div>

            <div class="md:w-1/2 relative">
                <div
                    class="absolute -top-10 -right-10 w-64 h-64 bg-[#023A82] rounded-full blur-3xl opacity-50 -z-10"
                ></div>

                <div
                    class="relative rounded-2xl overflow-hidden shadow-2xl border-[12px] border-white"
                >
                    <img
                        src="../assets/images/plombier.jpg"
                        alt="Artisan au travail"
                        class="w-full h-auto object-cover"
                    />
                </div>

                <div
                    class="absolute -bottom-6 -left-6 bg-white p-4 rounded-xl shadow-xl border border-gray-50 hidden md:block"
                >
                    <div class="flex items-center gap-3">
                        <div
                            class="bg-[#023A82] p-2 rounded-full text-white"
                        ></div>
                        <div>
                            <p
                                class="tracking-[0.1em] text-xs text-slate-400 font-bold uppercase"
                            >
                                Disponibilité
                            </p>
                            <p class="text-sm tracking-wide font-bold text-slate-800">
                                24h/24 - 7j/7
                            </p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { ArrowRight } from "@lucide/vue";
</script>

<style>
#background {
background: #ccd9ff;
background: linear-gradient(184deg, rgba(204, 217, 255, 1) 0%, rgba(255, 255, 255, 1) 100%);
}
</style>
