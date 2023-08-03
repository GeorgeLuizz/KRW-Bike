<template>
    <div class="flex flex-col place-content-start">
        <div class="border-[1px] border-black p-[2px]  w-[300px] h-[50px] ">
            <div class="image-container  w-[39px] h-[39px]">
                <img :src="image" class="object-contain w-full h-full"/>
            </div>

            
        </div>
    </div>
</template>

<script setup>
    import { ref } from 'vue'

    const image = ref("/mercadopago.png")
</script>