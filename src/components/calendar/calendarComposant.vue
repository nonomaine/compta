<script setup lang ='ts'>
import type { ProductInterface } from '@/interfaces/Product.interface';
import {computed, ref} from'vue'

defineProps<{
  product: ProductInterface;
}>();

 const yellow = computed(() =>(product: { color: string; }) => product.color === 'yellow' )
//const boxYellow = computed(() =>
 //product.filter(product => product.color === 'yellow')
 //);

const box=ref(true);


</script>

<template>
    <div  class="list-mission-box d-flex flex-column align-items-center justify-content-center pb-10">
                <h4 class="p-10">{{ product.date }}</h4>
                <div v-if="product.color === 'yellow'" :class="{boxyellow: box}" class="box-white d-flex flex-column align-content-around">
                  <h4 class="pl-5">{{ product.refmission }}</h4>
                  <p class="pl-5">{{ product.description }}</p>
                  <p class="pl-5">{{ product.horaire }}</p>
                  
                  
                </div>
                <div v-else-if="product.color === 'green'" :class="{boxgreen: box}" class="box-white d-flex flex-column align-content-around">
                  <h4 class="pl-5">{{ product.refmission }}</h4>
                  <p class="pl-5">{{ product.description }}</p>
                  <p class="pl-5">{{ product.horaire }}</p>
                  
                  
                </div>
                <div v-else="product.color === 'blue'" :class="{boxblue: box}" class="box-white d-flex flex-column align-content-around">
                  <h4 class="pl-5">{{ product.refmission }}</h4>
                  <p class="pl-5">{{ product.description }}</p>
                  <p class="pl-5">{{ product.horaire }}</p>
                  
                  
                </div>
              </div>
</template>

<style lang="scss" scoped>
.list-mission-box{
  width: 90%;
  height: 200px;
  background: var(--gray-2);
  border-radius: 15px;
  border:var(--border);

}
.box-white{
  height: 70%;
  width: 80%;
  background: white;
  border-radius: 5px;
  border-right: 5px solid var(--fourth-1);
}

.boxyellow{
  height: 70%;
  width: 80%;
  background: white;
  border-radius: 5px;
  border-right: 5px solid var(--second-1);
}
.boxblue{
  height: 70%;
  width: 80%;
  background: white;
  border-radius: 5px;
  border-right: 5px solid var(--third-1);
}
.boxgreen{
  height: 70%;
  width: 80%;
  background: white;
  border-radius: 5px;
  border-right: 5px solid var(--fourth-1);
}
h2, h4{
  color: var(--text-segondary-color)
}
p{
    font-size: 14px;
    margin: auto;
    
}
</style>