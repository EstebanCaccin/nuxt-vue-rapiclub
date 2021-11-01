<template>
    <div id="carousel">
        <VueSlickCarousel v-bind="settings">
            <div
                class="carousel-card"
                v-for="(item, it) in items"
                :key="it"
                v-bind:style="{ background: 'url(' + item.imagebackground + ')' }"
            >
                <div class="mb-8 rounded-full h-36 w-36 bg-white bg-carousel-card">
                    <img class="h-10 w-16 flex items-center jusitfy-center" :src="item.name" alt />
                </div>
                <div class="text-center carousel-card-info">
                    <button
                        class="text-white font-medium text-sm py-2 px-4 rounded-full"
                        v-bind:class="[item.classubname]"
                    >{{ item.subname }}</button>

                    <h4
                        class="text-xl text-gray-400 font-black"
                        v-bind:class="[item.classdiscount]"
                    >
                        <span class="font-extralight">Hasta</span>
                        {{ item.discount }}
                    </h4>
                    <p class="text-sm font-bold" v-bind:class="[item.classlevel]">
                        <span>
                            <i v-bind:class="item.icon"></i>
                        </span>
                        {{ item.level }}
                    </p>
                </div>
            </div>
        </VueSlickCarousel>
    </div>
</template>
 
<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
// optional style for arrows & dots
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
import './Carousel.css'

export default {
    name: 'Carousel',
    components: { VueSlickCarousel },
    data() {
        return {
            settings: {
                "dots": false,
                "infinite": true,
                "speed": 500,
                "slidesToShow": 4,
                "slidesToScroll": 4,
                "initialSlide": 0,
                "responsive": [
                    {
                        "breakpoint": 1024,
                        "settings": {
                            "slidesToShow": 3,
                            "slidesToScroll": 3,
                            "infinite": true,
                            "dots": true
                        }
                    },
                    {
                        "breakpoint": 600,
                        "settings": {
                            "slidesToShow": 2,
                            "slidesToScroll": 2,
                            "initialSlide": 0
                        }
                    },
                    {
                        "breakpoint": 480,
                        "settings": {
                            "slidesToShow": 1,
                            "slidesToScroll": 1
                        }
                    }
                ]
            },
            items: [
                {
                    name: "/netflix-logo.png",
                    subname: "Recreación",
                    classubname: "bg-blue-500 hover:bg-blue-900",
                    imagebackground: "/netflix.jpg",
                    discount: "10% OFF",
                    classdiscount: "text-blue-500",
                    level: "Nivel 1",
                    classlevel: "text-red-500",
                    icon: "fas fa-check",
                },
                {
                    name: "/cabify-logo.png",
                    subname: "Recreación",
                    classubname: "bg-blue-500 hover:bg-blue-900",
                    imagebackground: "/cabify.jpg",
                    discount: "10% OFF",
                    classdiscount: "text-blue-500",
                    level: "Nivel 1",
                    classlevel: "text-red-500",
                    icon: "fas fa-check",
                },
                {
                    name: "/alto-palermo-logo.png",
                    subname: "Compras",
                    classubname: "bg-black hover:bg-gray-600",
                    imagebackground: "/altopalermo.jpg",
                    discount: "15% OFF",
                    classdiscount: "text-black-500",
                    level: "Nivel 3",
                    classlevel: "text-black-500",
                    icon: "fas fa-lock"
                },
                {
                    name: "/fibertel-logo.png",
                    subname: "Tecnología",
                    classubname: "bg-green-500 hover:bg-green-900",
                    imagebackground: "/fibertel.jpg",
                    discount: "20% OFF",
                    classdiscount: "text-green-500",
                    level: "Nivel 4",
                    classlevel: "text-red-500",
                    icon: "fas fa-lock"
                },
                {
                    name: "/ypf-logo.png",
                    subname: "Combustible",
                    classubname: "bg-purple-500 hover:bg-purple-900",
                    imagebackground: "/ypf.jpg",
                    discount: "10% OFF",
                    classdiscount: "text-purple-500",
                    level: "Nivel 1",
                    classlevel: "text-black-500",
                    icon: "fas fa-check",
                },
                {
                    name: "/fabric-logo.png",
                    subname: "Recreación",
                    classubname: "bg-blue-500 hover:bg-blue-900",
                    imagebackground: "/fabric.jpg",
                    discount: "10% OFF",
                    classdiscount: "text-blue-500",
                    level: "Nivel 1",
                    classlevel: "text-red-500",
                    icon: "fas fa-check",
                },
                {
                    name: "/jumbo-logo.png",
                    subname: "Compras",
                    classubname: "bg-black hover:bg-gray-600",
                    imagebackground: "/jumbo.jpg",
                    discount: "15% OFF",
                    classdiscount: "text-black-500",
                    level: "Nivel 3",
                    classlevel: "text-black-500",
                    icon: "fas fa-lock"
                },
                {
                    name: "/burger-king-logo.png",
                    subname: "Recreación",
                    classubname: "bg-blue-500 hover:bg-blue-900",
                    imagebackground: "/burger-king.jpg",
                    discount: "10% OFF",
                    classdiscount: "text-blue-500",
                    level: "Nivel 1",
                    classlevel: "text-red-500",
                    icon: "fas fa-check",
                },
                {
                    name: "/dexter-logo.png",
                    subname: "Compras",
                    classubname: "bg-black hover:bg-gray-600",
                    imagebackground: "/dexter.jpg",
                    discount: "15% OFF",
                    classdiscount: "text-black-500",
                    level: "Nivel 3",
                    classlevel: "text-black-500",
                    icon: "fas fa-lock"
                },
            ]
        }
    },
}
</script> 