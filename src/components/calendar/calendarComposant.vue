<script setup lang ='ts'>
import type { ProductInterface } from '@/interfaces/Product.interface';

defineProps<{
  product: ProductInterface;
}>();


</script>

<template>
    <div class="list-mission-box d-flex flex-column align-items-center justify-content-center pb-10">
                <h4 class="p-10">{{ product.date }}</h4>
                <div class="box-white d-flex flex-column align-content-around">
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
h2, h4{
  color: var(--text-segondary-color)
}
p{
    font-size: 14px;
    margin: auto;
    
}
</style>