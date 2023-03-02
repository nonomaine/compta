<script setup lang="ts">
import type { ProductInterface } from '../interfaces/Product.interface';
import calendarList from './calendar/calendarList.vue'
import {computed, ref} from'vue'
import product from '@/data/product';
import modal from './modal/ModalPage.vue'



 defineProps<{
  products: ProductInterface[];
  
}>();

 const emit = defineEmits<{
   (e: 'checkBoxYellow', productColor: string): void;
 }>();

 
const open =ref(false);

const openCloseText=computed(() => 
open ? 'Nouvelle Mission' : 'Fermer la modal')



const show =ref(false);
const showGreen =ref(false);
const showYellow =ref(false);
const showBlue =ref(false);

const allBox = computed(() =>
  product.filter(product => product)
);
const boxGreen = computed(() =>
  product.filter(product => product.color === 'green')
);
const boxYellow = computed(() =>
  product.filter(product => product.color === 'yellow')
);
const boxBlue = computed(() =>
  product.filter(product => product.color === 'bleu')
);



</script>

<template>
  
    <div class="container-block d-flex flex-column">
     
       <div class="container-btn d-flex flex-row align-items-center mr-30" >
         <button @click="open = !open" class="btn btn-primary d-flex flex-row align-items-center">
          <img class="icon" src="../assets/icons/plus.png " width="15"  alt="">{{ openCloseText }}
         </button>
       </div>

       <div class="container-calendrier d-flex flex-column ml-30">
         <div class="intro d-flex flex-row align-items-center">
           <h2 class="m-30">Mission</h2>
         </div>
         <div class="d-flex flex-row align-items-center justify-content-center">
            <h4 class=" d-flex flex-row align-items-center"> <span class="pr-20">
               <img src="../assets/icons/left-arrow.png" width="15" alt=""></span> Février <span class="pl-20">
              <img src="../assets/icons/right-arrow.png" width="15" alt=""></span>
            </h4>
          </div>
         <div class= "chips-all d-flex flex-row align-items-center justify-content-center p-30">
            <div class="chips-total">
              <button class="chips btn-segondary m-30">Hebdomadaire</button>
               <img src="../assets/icons/next-week.png" class="img1" width="30" alt="">
            </div>
            <div class="chips-total ">
              <button  class="chips btn-segondary m-30">Mensuelle</button>
               <img src="../assets/icons/appointment.png" class="img1" width="30" alt="">
            </div>
            <div class="chips-total">
              <button class="chips btn-segondary m-30">Trimestrielle</button>
               <img src="../assets/icons/business-report.png" class="img1" width="30" alt="">
            </div>
          </div>
          <div class="mission">
            <div class="control-mission d-flex flex-column ">
              <h4>Priorité Taches</h4>
              <div class="d-flex flex-row align-items-center mt-30">
                <input @click="show=!show" class="checkbox" type="checkbox"  name="scales" >
                <label class="p-10" for="scales">Toutes</label>
              </div>
              <div class="d-flex flex-row align-items-center mt-30">
                <input @click="showGreen=!showGreen" class="checkbox checkbox-basse" type="checkbox"  name="scales">
                <label class="p-10" for="scales">Basses</label>
              </div>
              <div class=" d-flex flex-row align-items-center mt-30">
                <input @click="showYellow=!showYellow" class="checkbox checkbox-normal"  type="checkbox"  name="scales"  >
                <label class="p-10" for="scales">Normales </label>
              </div>
              <div class=" d-flex flex-row align-items-center mt-30">
                <input @click="showBlue=!showBlue" class="checkbox checkbox-haute"  type="checkbox"  name="scales">
                <label class="p-10" for="scales">Hautes</label>
              </div> 
            </div>
            <div class="list-mission">

              <calendarList v-if="show" :products="allBox"  />
              <calendarList v-else-if="showGreen" :products="boxGreen"  />
              <calendarList v-else-if="showYellow" :products="boxYellow"  />
              <calendarList v-else-if="showBlue" :products="boxBlue"  />
              <calendarList v-else :products="products"/>
              
              
              


            </div>
          </div>

      </div>

    </div>
    <modal v-show="open" @close-modal="open = false"/>

</template>

<style lang="scss" scoped>

.container-block{
  width:100%;
  height:100%;
 
}

.container-btn{
  height: 15%;
  justify-content: flex-end;
}

.container-calendrier{
  width:85%;
  background: white;
  height: 1200px;
  border-radius: 30px;
  border: var(--border);
  box-shadow: 0px 4px 6px -1px rgba(0, 0, 0, .1);
  padding-bottom: 30px;
}
.icon{
  margin-right: 10px;
}
.intro{
  
  height:20%;
  justify-content: flex-start;
}
.chips-total{
  position: relative;
  padding-top: 50px;
}


.img1{
  position: absolute;
  right: 40%;
  top:10%;   
}

.chips-all{
  width: 80%;
  border-bottom: var(--border-1);
  margin:0 auto;
}

h2, h4{
  color: var(--text-segondary-color)
}
.mission{
  height: 800px;
  display: grid;
  grid-template-areas: 'control-mission' 'list-mission';
  grid-template-columns: 20% 80%;
    
}
.control-mission h4{
  margin: 30px auto;
}
input[type=checkbox] {
    -webkit-appearance: none;
    -moz-appearance: none;
    -ms-appearance: none;
}
input[type=checkbox] {
    border-radius: 4px;
    height: 15px;
    width: 15px;
    background: #fff;
    border: 2px solid #666f7b;
}

input.checkbox{
  margin-left:30PX;
}
input[type=checkbox].checkbox-basse{
  border: 2px solid var(--fourth-1);
}
input[type=checkbox].checkbox-normal{
  border: 2px solid var(--second-1);
}
input[type=checkbox].checkbox-haute{
  border: 2px solid var(--third-1);
}

input[type="checkbox"]:checked {
  
 
  position: relative;
  &:before {
    font-family: FontAwesome ;
    content: "\f00c";
    display: block;
    color: grey;
    font-size: 13px;
    position: absolute;
  }
}


</style>