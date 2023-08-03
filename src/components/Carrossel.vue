<template>
    <div class="border-[1px] border-black p-8 w-[600px]"  >
        <carousel :itens-to-show="1" :wrap-around="false" v-model="currentSlide" >
            <slide v-for="(slide) in image" :key="slide">
                <div class="carousel__item ">
                    <img :src="slide" class="object-contain w-full h-full" />
                </div>
            </slide>
        </carousel>
        <carousel id="thumbnails" :items-to-show="3" :wrap-around="true" v-model="currentSlide" ref="carousel" class="space-x-3">
            <Slide v-for="(slide,index) in image" :key="slide">
                <div class="image-container w-[70px] h-[70px]" @click="slideTo(index)" >
                    <img :src="slide" class="border-[1px] border-black w-full h-full object-contain " />
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