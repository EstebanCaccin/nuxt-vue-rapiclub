<template>
    <footer>
        <div class="flex flex-wrap justify-center">
            <div class="w-full sm:w-1/1 md:w-1/4 lg:w-1/4 xl:w-3/12 p-4 mb-1">
                <h1 class="text-red-500 italic font-black text-3xl text-left">rapiclub</h1>
                <h4 class="text-red-500 text-sm text-left copyright-desktop pt-8">
                    Copyright 2020 S.A Rapiclub ©
                    Todos los derechos reservados
                </h4>
            </div>
            <div class="w-1/2 sm:w-2/4 md:w-1/3 lg:w-1/5 xl:w-2/12 pl-4 pt-4 mb-1">
                <h4
                    v-for="(benefit, b) in footerBenefit"
                    :key="b"
                    class="text-red-500 text-sm font-black text-left pt-4"
                >{{ benefit }}</h4>
            </div>
            <div class="w-1/2 sm:w-2/4 md:w-1/3 lg:w-1/5 xl:w-2/12 pl-4 pt-4 mb-1">
                <h4
                    v-for="(help, h) in footerHelp"
                    :key="h"
                    v-bind:class="[help.class]"
                >{{ help.name }}</h4>
            </div>
            <div class="w-full sm:w-1/4 md:w-full lg:w-1/3 xl:w-1/3 p-4 mb-1 lg:mt-4">
                <h4 class="text-red-500 text-sm text-left md:text-center md:mr-20">Descargá la App</h4>
                <div class="flex justify-center apps-logo-desktop pt-6">
                    <img
                        class="m-auto pl-5 pt-5"
                        v-for="(image, i) in images"
                        :key="i"
                        :src="image.src"
                    />
                </div>
            </div>
            <div
                v-for="(image, i) in images"
                :key="i"
                class="w-2/2 sm:w-1/4 md:w-1/3 lg:w-1/3 xl:hidden p-4 mb-1 apps-logo-mobile"
            >
                <img class="m-auto" :src="image.src" />
            </div>
            <div class="w-full sm:w-2/3 md:w-3/5 lg:w-1/3 xl:hidden p-4 mb-1">
                <h4 class="text-red-500 text-sm text-left copyright-mobile">
                    Copyright 2020 S.A Rapiclub ©
                    Todos los derechos reservados
                </h4>
            </div>
        </div>
    </footer>
</template>

<script>
import './Footer.css';
export default {
    name: 'Footer',

    data() {
        return {
            footerBenefit: [
                'Conocé Rapiclub',
                'Canjeá tus puntos',
                'Beneficios',
            ],
            footerHelp: [
                {
                    name: 'Ayuda',
                    class: 'text-red-500 text-sm font-black text-left pt-4',
                },
                {
                    name: 'Consultas',
                    class: 'text-red-500 text-sm text-left pt-4',
                },
                {
                    name: 'Preguntas frecuentes',
                    class: 'text-red-500 text-sm text-left',
                },
                {
                    name: 'Regamento',
                    class: 'text-red-500 text-sm text-left',
                }
            ],
            images: [
                {
                    src: '/app-store-logo.png'
                },
                {
                    src: '/google-play-logo.png'
                }
            ],
        }
    }
};
</script>

<style scoped>
</style>