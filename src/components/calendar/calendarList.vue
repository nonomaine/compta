<script setup lang="ts">
import calendarComposant from './calendarComposant.vue'
import type { ProductInterface } from '@/interfaces/Product.interface';



defineProps<{
  products: ProductInterface[];
  
}>();


const emit = defineEmits<{
   (e: 'checkBoxYellow', productColor:string): void;
}>();

</script>

<template>
    <div class="grid mt-20">

        <calendarComposant v-for="product of products" :product="product" @check-box-yellow="emit('checkBoxYellow',$event)"/>
      
    </div>
</template>

<style lang="scss" scoped>
.grid{
    
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    grid-auto-rows: 200px;
    gap: 10px;
  

}
</style>