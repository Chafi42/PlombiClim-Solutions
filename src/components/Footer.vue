<template>
    <footer
        class="w-full bg-white border-t border-gray-100 pt-12 pb-8 px-6 md:px-16 font-sans"
    >
        <div class="max-w-7xl mx-auto">
            <div
                class="flex flex-col md:flex-row justify-between items-center gap-8 mb-10"
            >
                <div
                    class="flex flex-col items-center md:items-start group cursor-pointer"
                >
                    <div class="flex flex-col leading-none">
                        <img
                            src="@/assets/images/PlombiClimSolutions.png"
                            alt="Logo PlombiClim"
                            class="h-16 md:h-20 w-auto mb-1"
                        />
                    </div>
                </div>

                <nav
                    class="flex flex-wrap justify-center gap-x-8 gap-y-4 text-slate-500 text-[13px] font-medium"
                >
                    <a href="#" class="hover:text-[#023A82] transition-colors"
                        >Mentions Légales</a
                    >
                    <a href="#" class="hover:text-[#023A82] transition-colors"
                        >Politique de Confidentialité</a
                    >
                    <a href="#" class="hover:text-[#023A82] transition-colors"
                        >Plan du site</a
                    >
                </nav>

                <div class="flex items-center gap-3">
                    <a
                        href="#"
                        class="p-3 rounded-full bg-white shadow-sm hover:shadow-md transition-all"
                    >
                        <i
                            class="fa-brands w-5 h-5 text-center fa-instagram"
                            style="color: #023a82"
                        ></i>
                    </a>

                    <a
                        href="#"
                        class="p-3 rounded-full bg-white shadow-sm hover:shadow-md transition-all"
                    >
                        <i
                            class="fa-brands fa-facebook-f w-5 h-5 text-center"
                            style="color: #023a82"
                        ></i>
                    </a>

                    <a
                        href="#"
                        class="p-3 rounded-full bg-white shadow-sm hover:shadow-md transition-all"
                    >
                        <i
                            class="fa-brands fa-snapchat w-5 h-5 text-center"
                            style="color: #023a82"
                        ></i>
                    </a>
                </div>
            </div>

            <div class="flex flex-col gap-8 mb-12">
                <p class="text-slate-400 text-xs text-center tracking-wide">
                    © {new Date().getFullYear()} Signature Digitale.
                    Tous droits réservés.
                </p>
            </div>
        </div>
    </footer>
</template>
