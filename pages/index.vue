<template>
    <div id="home">
        <!-- Hero -->
        <div class="bg-nav h-80 md:h-96">
            <div class="flex flex-wrap justify-center">
                <div class="w-full mt-8">
                    <img
                        v-for="(image, i) in images"
                        :key="i"
                        :src="image.src"
                        class="musimundo-img ml-6"
                    />
                    <h1
                        class="text-white font-black text-left ml-6 text-3xl sm:text-4xl md:text-5xl lg:text-6xl"
                    >25% descuento</h1>
                    <h2
                        class="text-white font-thin text-left ml-6 text-2xl sm:text-3xl md:text-4xl lg:text-5xl"
                    >
                        este
                        <span
                            class="text-white font-black text-left text-2xl sm:text-3xl md:text-4xl lg:text-5xl"
                        >CyberMonday</span>
                    </h2>
                    <p
                        class="text-white font-thin text-left ml-6 text-base sm:text-1xl md:text-2xl lg:text-3xl"
                    >
                        con tu tarjeta rapiclub este
                        <br />4,5 y 6 de noviembre
                    </p>
                    <button
                        class="bg-red-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded flex justify-start ml-6 mt-4 font-base"
                    >Conocé más</button>
                </div>
            </div>
        </div>
        <!-- Hero end -->
        <!-- Search -->
        <div class="container m-auto mt-8">
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-4 py-12">
                <div class="flex flex-wrap justify-center">
                    <div class="w-full sm:w-1/2 m-auto pt-4">
                        <h2
                            class="ml-2 font-light text-xl text-left"
                        >Empezá a disfrutar de diferentes opciones para cada estilo de vida</h2>
                    </div>
                    <div class="w-full sm:w-1/2 m-auto">
                        <input
                            type="search"
                            class="bg-purple-white border border-red-600 focus:border-none p-4"
                            placeholder="¿Qué estas buscando"
                        />
                    </div>
                </div>
            </div>
            <!-- Search end -->
            <!-- Cards -->
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-4 py-12">
                <div class="grid grid-cols-2 sm:grid-cols-2 md:grid-cols-4 lg:grid-cols-4 gap-6">
                    <div v-for="(category, c) in categorys" :key="c" class="w-full">
                        <div class="card-card" v-bind:class="[category.background]">
                            <div class="flex justify-center">
                                <div class="w-1/2">
                                    <h3
                                        class="text-white text-left text-sm font-bold mt-5 ml-2"
                                    >{{ category.name }}</h3>
                                </div>
                                <div class="w-1/2">
                                    <i v-bind:class="[category.icon]"></i>
                                </div>
                            </div>
                            <div class="w-1/1">
                                <p
                                    class="text-xs text-left text-white mt-4 ml-2"
                                >{{ category.subname }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <!-- Cards end -->
            <Discont
            background="bg-green-400"
            discont=10
            title="falabella"
             />
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-4 py-12">
                <div class="bg-red-600 h-48 sm:h-auto">
                    <div class="flex flex-wrap justify-center">
                        <div class="w-full sm:w-1/2 m-auto p-4 flex justify-center">
                            <h2
                                class="ml-2 font-light text-xl text-white"
                            >Disfrutá de beneficios exclusivos y promociones increibles</h2>
                        </div>
                        <div class="w-full sm:w-1/2 m-auto flex justify-center">
                            <button
                                class="hover:bg-blue-700 text-white font-bold py-2 px-4 rounded flex justify-start ml-6 font-base border border-white text-center"
                            >Ver beneficios en mi ciudad</button>
                        </div>
                    </div>
                </div>
            </div>
            <!-- Benefit -->
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-4 py-12">
                <div class="flex justify-center mb-4 font-bold text-xl">
                    <h1 class="text-black font-normal text-3xl">
                        Estos son algunos de los
                        <br />beneficios que tenemos para vos
                    </h1>
                </div>
            </div>
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-4 py-12">
                <div class="flex justify-center mb-4 font-bold text-xl">
                    <h1 class="text-red-500">
                        <span>
                            <i class="far fa-star"></i>
                        </span>
                        Destacados
                    </h1>
                </div>

                <Carousel />
            </div>
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-4 py-12">
                <div class="flex justify-center mb-4 font-bold text-xl">
                    <h1 class="text-red-500">
                        <span>
                            <i class="far fa-grin-stars"></i>
                        </span>
                        Nuevos
                    </h1>
                </div>

                <Carousel />
            </div>
            <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-4 py-12">
                <div class="flex justify-center mb-4 font-bold text-xl">
                    <h1 class="text-red-500">
                        <span>
                            <i class="far fa-thumbs-up"></i>
                        </span>
                        Más elegidos
                    </h1>
                </div>

                <Carousel />
            </div>
            <!-- Benefit end -->
             <Discont
            background="bg-purple-400"
            discont=15
            title="SommierCenter"
             />
        </div>
    </div>
</template>

<script>
import './index.css';
import Carousel from '../components/Carousel/index.vue';
export default {
    layout: "default",
    data() {
        return {
            images: [
                {
                    src: "/logo-musimundo-white.png"
                }
            ],
            categorys: [
                {
                    name: "Tecnología",
                    subname: "Hogar en general",
                    icon: "fas fa-mobile-alt text-3xl text-white mt-4",
                    background: "bg-green-700"
                },
                {
                    name: "Compras",
                    subname: "Moda, jugueterías, belleza",
                    icon: "fas fa-shopping-bag text-3xl text-white mt-4",
                    background: "bg-indigo-900"
                },
                {
                    name: "Recreación",
                    subname: "Viajes, gastronomía, espectaculos",
                    icon: "fas fa-plane text-3xl text-white mt-4",
                    background: "bg-blue-600"
                },
                {
                    name: "Y más",
                    subname: "Combustibles, automotriz",
                    icon: "fas fa-car text-3xl text-white mt-4",
                    background: "bg-purple-600"
                }
            ]
        };
    },
    components: { Carousel }
}
</script>
<style>
#__nuxt {
    font-family: "Montserrat", sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}
.container {
    max-width: 1280px !important;
}
</style>