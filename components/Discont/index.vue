<template >
    <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-4 py-12 copyright-desktop">
        <div v-bind:class="background" class="flex flex-wrap">
            <div class="w-2/3">
                <div class="w-full p-4 mb-1">
                    <h1 class="text-white italic font-black text-3xl text-left ml-8">rapiclub</h1>
                    <h4 class="text-white text-7xl font-black text-left pt-4 ml-8">
                        {{ discont }}%
                        <span class="font-light">DESCUENTO</span>
                    </h4>
                </div>
            </div>
            <div class="w-1/3">
                <div class="flex flex-wrap">
                    <div class="w-full mt-8">
                        <h2 class="text-white text-4xl">
                            {{ title }}
                            <span>
                                <i class="fas fa-shopping-bag text-white text-5xl"></i>
                            </span>
                        </h2>
                        <h4 class="text-white text-xs font-semibold mt-4">
                            CON TU COMPRA DURANTE MARZO <br>
                            <span class="text-xs font-light">TODOS LOS DÍAS</span>
                        </h4>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        title: String,
        discont: Number,
        background: String,
    }
};
</script>