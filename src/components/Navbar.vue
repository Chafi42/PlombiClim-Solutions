<template class="">
    <header
        class="sticky  top-0 bg-white shadow-[0px_4px_20px_rgba(0,0,0,0.05)] py-4 px-4 sm:px-6 min-h-[70px]   z-50"
    >
        <div
            class="flex items-center justify-between  w-full max-w-screen-xl mx-auto"
        >
            <a href="#accueil" class="flex items-center gap-2 group">
                <img
                    src="@/assets/images/PlombiClimSolutions.png"
                    alt="logo"
                    class="h-12 md:h-22 w-auto object-contain transition-transform group-hover:scale-105"
                />
            </a>

            <nav class="hidden lg:flex items-center gap-8">
                <a
                    v-for="link in navLinks"
                    :key="link.href"
                    :href="link.href"
                    class="text-sm uppercase manrope tracking-[0.2em] hover:text-[#FC770A] transition-all duration-300 relative after:content-[''] after:absolute after:w-0 after:h-[2px] after:bg-[#FC770A] after:left-0 after:-bottom-1 hover:after:w-full after:transition-all"
                >
                    {{ link.name }}
                </a>
            </nav>

            <div class="flex items-center space-x-4">
                <a
                    @click="isMenuOpen = false"
                    href="#contact"
                    class="hidden sm:flex bg-[#FC770A] px-6 py-2.5 rounded-full text-white text-sm hover:scale-105 font-bold shadow-lg shadow-orange-200 transition-all active:scale-95"
                >
                    Demander un devis
                </a>

                <button
                    @click="isMenuOpen = true"
                    class="lg:hidden p-2 text-slate-900 hover:bg-slate-50 rounded-lg transition-colors"
                >
                    <svg
                        class="w-8 h-8  hover:transition-transform hover:scale-110"
                        fill="none"
                        stroke="currentColor"
                        viewBox="0 0 24 24"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M4 6h16M4 12h16m-7 6h7"
                        />
                    </svg>
                </button>
            </div>

            <Transition name="slide">
                <div v-if="isMenuOpen" class="fixed inset-0 z-[100] lg:hidden">
                    <div
                        class="absolute inset-0 bg-slate-900/40 backdrop-blur-sm transition-opacity"
                        @click="isMenuOpen = false"
                    ></div>

                    <div
                        class="absolute top-0 left-0 w-[80%] max-w-[350px] h-full bg-white shadow-2xl p-6 flex flex-col"
                    >
                        <div
                            class="flex items-center justify-between mb-10 border-b border-slate-50 pb-4"
                        >
                            <img
                                src="@/assets/images/PlombiClimSolutions.png"
                                alt="logo"
                                class="h-10 w-auto"
                            />
                            <button
                                @click="isMenuOpen = false"
                                class="p-2 bg-slate-50 rounded-full text-slate-500 hover:rotate-90 transition-all duration-300"
                            >
                                <svg
                                    class="w-6 h-6 "
                                    fill="none"
                                    stroke="currentColor"
                                    viewBox="0 0 24 24"
                                >
                                    <path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        stroke-width="2"
                                        d="M6 18L18 6M6 6l12 12"
                                    />
                                </svg>
                            </button>
                        </div>

                        <nav class="flex flex-col gap-2">
                            <a
                                v-for="link in navLinks"
                                :key="link.href"
                                :href="link.href"
                                @click="isMenuOpen = false"
                                class="text-lg font-bold p-4 rounded-xl hover:bg-orange-50 hover:text-[#FC770A] transition-all uppercase tracking-widest text-[#475569]"
                            >
                                {{ link.name }}
                            </a>
                        </nav>

                        <div class="mt-auto pt-6 border-t border-slate-50">
                            <a
                                href="#contact"
                                @click="isMenuOpen = false"
                                class="w-full bg-[#FC770A] text-white py-4 rounded-xl font-bold flex items-center justify-center hover:scale-105 transition-transform gap-2"
                            >
                                Demander un devis
                            </a>
                        </div>
                    </div>
                </div>
            </Transition>
        </div>
    </header>
</template>

<script setup>
import { ref } from "vue";

const isMenuOpen = ref(false);

const navLinks = [
    { name: "Accueil", href: "#accueil" },
    { name: "Spécialités", href: "#specialites" },
    { name: "Services", href: "#services" },
    { name: "Témoignages", href: "#temoignages" },
    { name: "Contact", href: "#contact" },
];
</script>

<style scoped>

    /* Animation Slide-in */
    .slide-enter-active,
    .slide-leave-active {
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    }

    .slide-enter-from,
    .slide-leave-to {
    transform: translateX(-100%);
    opacity: 0;
    }

    /* Empêcher le scroll quand le menu est ouvert */
    :global(body.menu-open) {
    overflow: hidden;
    }
</style>
