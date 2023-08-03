<template>
    <div class="border-[1px] border-black p-8">
        <carousel :itens-to-show="1" :wrap-around="false" v-model="currentSlide">
            <slide v-for="(slide) in image" :key="slide">
                <div class="carousel__item">
                    <img :src="slide" />
                </div>
            </slide>
        </carousel>
        <carousel id="thumbnails" :items-to-show="4" :wrap-around="true" v-model="currentSlide" ref="carousel">
            <Slide v-for="(slide,index) in image" :key="slide">
                <div id="carousel__item" @click="slideTo(index)" >
                    <img :src="slide" class="border-[1px] border-black w-25 h-25 object-cover" />
                </div>
            </Slide>
            <template #addons>
                <navigation />
            </template>
        </carousel>
    </div>
</template>
 
<script setup>
    import { ref } from 'vue'
    import { Carousel, Slide, Navigation } from 'vue3-carousel'
    import 'vue3-carousel/dist/carousel.css'
    
    const currentSlide = ref(0)
    
    function slideTo(val) {
        currentSlide.value = val
    }

    const image = ref(
        [
            "./public/15111710074-01 1.png",
            "./public/58a1bb296d.png",
            "./public/2398c8a938-1.png",
            "./public/2398c8a938.png"

        ]
    )
</script>