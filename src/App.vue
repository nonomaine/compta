<script setup lang="ts">
import Theheader from'./components/header.vue';
import Thenav from'./components/nav.vue';
import corps from './components/corps.vue';
import data from './data/product';
import { reactive } from 'vue';
import type{ ProductInterface } from './interfaces/Product.interface';
import {computed, ref} from'vue'



const state = reactive<{
  products: ProductInterface[];
  
}>({
  products: data,
 
});


  
function checkBoxYellow(productColor: string) : void{
  const product = state.products.find((product) => product.color === productColor);
  if(product){

    state.products.filter(product => product.color === 'yellow');
  }
   
}

function changeClass(){
  document.body.classList.toggle('app-containerReduc');
}



const boxYellow = computed(() =>
  state.products.filter(product => product.color === 'yellow')
);






</script>

<template>
  <div class="app-container" >
    <Theheader class="header" @change-class="changeClass"/>
    <Thenav class="nav" />
    <corps :products="state.products" @check-box-yellow="checkBoxYellow" class="corps"/>
    
    
   
  </div>
  
</template>

<style lang = "scss">
@import './assets/base.scss';
@import './assets/debug.scss';

.app-container {
  width : 100%;
  min-height: 100vh;
  display: grid;
  grid-template-areas: 'header header' 'nav corps' ;
  grid-template-columns: 15% 85%;
  grid-template-rows: 90px auto ;
}
// .app-containerReduc {
//   width : 100%;
//   min-height: 100vh;
//   display: grid;
//   grid-template-areas: 'header header' 'nav corps' ;
//   grid-template-columns: 5% 95%;
//   grid-template-rows: 90px auto ;
// }

.header {
  grid-area: header;
}
.nav {
  grid-area: nav;
}
.corps {
  grid-area: corps;
}


</style>
