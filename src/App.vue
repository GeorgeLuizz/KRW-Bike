<template>
    <div>
      <!--Notificação-->
        <div class="bg-[#252F97] text-white text-sm font-[Roboto] text-center">
            {{aviso}} 
        </div>


        <!--Menu com Logo-->
        <div id="logo" class="bg-white text-sm border-y-2 p-3 flex items-center justify-center">
            <img class="w-24 h-auto" src="./assets/LOGO1.png" alt="Logo" />
        
            <div class="relative ml-4">
                <input type="text" class="rounded input-with-icon text-xs border-y-2 px-2 py-1 w-64 " placeholder="O que você precisa?"/>
                <div class="absolute inset-y-3 right-3 pl-5 flex items-center pointer-events-none">
                    <img src="./assets/Group 200.png" alt="pesquisa" />
                </div>
        </div>
    
        <div class="ml-4">
          <a href="/fale-conosco" class="text-blue-600 hover:underline">Fale Conosco</a>
          <a href="/fale-conosco" class="text-blue-600 hover:underline">Fale Conosco</a>
        </div>
    
        <div class="ml-4">
          <p class="text-gray-600 w-32">Olá, {{ cliente }}, temos novidades pra você</p>
        </div>
        </div>


        <!--Menu Navegação-->
        <nav class="flex items-center justify-center bg-whtie border-b-4 text-xs">
            <div class="flex space-x-4">
                <a href="#" class="text-[#15104B] hover:text-gray-600">Bicicleta KRW</a>
                <a href="#" class="text-gray-800 hover:text-gray-600">Quadros KRW</a>
                <a href="#" class="text-gray-800 hover:text-gray-600">Bicicletas</a>
                <a href="#" class="text-gray-800 hover:text-gray-600">Ofertas</a>
                <a href="#" class="text-gray-800 hover:text-gray-600">Categorias</a>
            </div>
            <button class="items-start px-11 py-2 bg-[#252F97] text-white rounded ml-20">OFERTAS IMPERDIVEIS</button>
        </nav>
        
        
        <!--Informações-->
        <Infos />
        
        
        <!--Pagina-->
        <div class="flex">
            <!--Lado Esquerdo-->
            <div class="w-1/2 px-8">
                <Carrossel />
            </div>
            
            
            <!--Lado Direito-->
            <div class="w-1/2 px-8">
                <h1 class="text-lg mb-4">{{tituloProduto}}</h1>
                <p class="text-xs">Tamanho do quadro</p>
                <div id="quadrosBike" class="flex items-center justify-right space-x-2 mb-4">
                  <div class="border-black border-[0.5px] rounded text-xs w-8 p-1 text-center">
                      15,5'
                  </div>
                  <div class="border-black border-[0.5px] rounded text-xs w-8 p-1 text-center">
                      17'
                  </div>
                  <div class="border-black border-[0.5px] rounded text-xs w-8 p-1 text-center">
                      19'
                  </div>
                  <div class="border-black border-[0.5px] rounded text-xs w-8 p-1 text-center">
                      21'
                  </div>
                </div>
                <CorBike />
                <FormaPagamento :image="'/images.png'" :titulo="'Cartão de Crédito'" :condicao="'Parcela'" :opcao="true"/>
                <FormaPagamento :image="'/pix-foto-site-1.png'" :titulo="'Pix'" :condicao="'Parcela'" :opcao="true"/>
                <FormaPagamento :image="'/image 55.png'" :titulo="'Boleto'" :condicao="'R$2.999,00'"/>
                <FormaPagamento :image="'/mercadopago.png'" :titulo="'Mercado Pago'" :condicao="'R$2.999,00'"/>
                <button class="justify-start px-11 py-2 bg-[#000000] text-white rounded mt-4">COMPRAR AGORA</button>
            </div>
        </div>

    </div>
</template>
<script setup>

    import Infos from './components/Infos.vue'
    import Carrossel from './components/Carrossel.vue'
    import CorBike from './components/CorBike.vue'
    import FormaPagamento from './components/FormaPagamento.vue'


    import { ref } from 'vue';
    const aviso = ref("Este mês estaremos com descontos de até 40%")
    const cliente = ref("Daniel")

    const tituloProduto = ref("Bicicleta de aluminio aro 29 KSW Shimano TZ Vel Ltx KRW20")
</script>
