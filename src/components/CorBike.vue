<template>
    <p class="text-xs">Escolha a Cor</p>
    <div class="flex justify-start space-x-1 items-center mb-4">
        <div v-for="(slide, ind) in images" :key="ind" @click="selecionarCor(ind)" class="border-[1px] border-black p-[2px] cursor-pointer" :style="(indiceImagemSelecionada == ind) ? 'border-width: 2px' : ''">
            <div class="image-container  w-[39px] h-[39px]">
                <img :src="slide.url" class="object-contain w-full h-full"/>
            </div>
            <div class="w-[29px] h-[3px] mx-auto mb-[1px]" :style="'background-color: ' + slide.cor">
            </div>
        </div>
    <a href="/fale-conosco" class="text-grey hover:underline text-xs">Mais Cores</a>
    </div>
</template>

<script setup>
    import { ref } from 'vue'

    const indiceImagemSelecionada = ref(0)

    const images = ref([
        {url: "/vermelha.png", cor: "#EF593C"},
        {url: "/azul.png", cor: "#60D0FC"},
        {url: "/rosa.png", cor: "#DC316D"},
        {url: "/verde.png", cor: "#818181"},
        {url: "/cinza.png", cor: "#DFDFDF"},
    ])

    function selecionarCor(indice) {
        indiceImagemSelecionada.value = indice

    }
</script>