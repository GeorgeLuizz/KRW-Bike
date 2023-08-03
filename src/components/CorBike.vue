<template>
    <div class="flex items-center justify-start space-x-32 m-4">
    <Carousel :items-to-show="2.5" :wrap-around="true">
        <Slide v-for="slide in images" :key="slide">
            <div class="carousel__item">
                <img :src="slide" />
            </div>
        </Slide>
    
        <template #addons>
            <Navigation />
        </template>
    </Carousel>
    <a href="/fale-conosco" class="text-grey hover:underline text-xs">Mais Cores</a>
    </div>
</template>

<script setup>
    import { ref } from 'vue'
    import { Carousel, Navigation, Slide } from 'vue3-carousel'

    import 'vue3-carousel/dist/carousel.css'

    const images = ref([
        "/vermelha.png",
        "/rosa.png",
        "/verde.png",
        "/azul.png"
    ])
</script>