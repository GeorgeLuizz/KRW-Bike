<template>
    <div class="flex place-content-start w-[350px] h-[40px] border-[1px] border-grey justify-between items-center text-sm p-3 mt-2">
        <div class="flex items-center">
            <div class=" p-[2px]">
                <div class="image-container  w-[39px] h-[39px]">
                    <img :src="image" class="object-contain w-full h-full"/>
                </div>
            </div>
            <div> {{ titulo }}</div>
        </div>

        <div class="flex items-center">
            <span>
                {{ condicao }}
            </span>
            <span v-if="opcao == true"> 
                <img src="/opcao.png" alt="">
            </span>
        </div>
        
    </div>
</template>

<script setup>
    
    const props = defineProps({
        image: String,
        titulo: String,
        condicao: String,
        opcao: Boolean
    })

</script>