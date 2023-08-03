<template>
    <div class="flex justify-start space-x-1 items-center mb-4">
        <div 
        v-for="(tamanho,index) in tamanhos" 
        :key="tamanho.tamanho" 
        @click="selecionarTamanho(index)" 
        class=" border-black border-[0.5px] rounded text-xs w-8 h-8 p-1 cursor-pointer" 
        :style="(tamanhoSelecionado == index) ? 'border-width: 2px' : ''">
            <div class="image-container  w-[39px] h-[39px]">
                {{ tamanho.tamanho }}
            </div>
            <div class="w-[29px] h-[3px] mx-auto mb-[1px]" :style="'background-color: ' + tamanho.tamanho">
            </div>
        </div>
    </div>
</template>

<script setup>
    import { ref } from 'vue'

    const tamanhoSelecionado = ref(0)

    const tamanhos = ref([
        {tamanho: "15.5"},
        {tamanho: "17"},
        {tamanho: "19"},
        {tamanho: "21"},
    ])

    function selecionarTamanho(indice) {
        tamanhoSelecionado.value = indice

    }
</script>