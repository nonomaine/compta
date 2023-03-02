<script setup lang="ts">
import { computed, ref } from 'vue';

const emit = defineEmits<{
   (e: 'closeModal'): void
}>()

</script>

<template>
<div class="modal">
    
        <div class="modal__inner">
           <div class="titre btn d-flex flex-row justify-content-between align-items-center">
               <h2>Mission</h2>  
               <button class="btn btn-segondary justify-content-end" @click="$emit('closeModal')">Fermer</button>
           </div> 
           <div class="mission btn d-flex flex-column justify-content-center">
                  <h3 class="p-50"> Missions: <span class="pl-20"> Déclarez votre nouvelle mission</span></h3>
                <div class="input-control">
                  <input type="text" id="search" placeholder="Titre de la nouvelle mission">
                </div>
                <div class="d-flex flex-row justify-content-between align-items-center">
                  <div class="select-control" >
                    <select  name="entreprise">
                      <option value=""> Entreprise </option>
                      <option value="Axa"> Axa </option>
                      <option value="Adecco"> Adecco </option>
                      <option value="Adéquat">Adéquat  </option>
                      <option value="Sfr"> Sfr </option>
                    </select>
                  </div>
                  <button class="btn btn-primary d-flex flex-row align-items-center"><img class="icon" src="/src/assets/icons/plus.png " width="15"  alt=""> Ajouter entreprise</button>
                </div>
                <h3 class="pt-100">Description</h3>
                <textarea class="mt-50 ml-30" placeholder="Description"></textarea>
                <h3 class="pt-100">Calendrier</h3>
                <div class="date d-flex flex-row align-items-center justify-content-between mt-30">
                  <input type="date" name="" id="">
                  <input type="date" name="" id="">
                </div>
                
                  <div class="select-controlwhite d-flex justify-content-end ">
                    <label for="">Durée journalière</label>
                    <select name="entreprise">
                      <option value="Personnalisée"> Personnalisée </option>
                      <option value="Matinée"> Matinée </option>
                      <option value="Après midi"> Aprés-midi </option>
                      <option value="Journée">Journée  </option>
                      
                    </select>
                  </div> 
                  <div class="select-controlwhite d-flex justify-content-end mb-50">
                    <label for="">Quantité</label>
                    <select name="entreprise">
                      <option value=""> Quantité </option>
                      <option value="1"> 1 </option>
                      <option value="2"> 2 </option>
                      <option value="3">3  </option>
                      <option value="4"> 4 </option>
                      <option value="5"> 5 </option>
                      <option value="6"> 6 </option>
                      <option value="7"> 7 </option>
                      <option value="8"> 8 </option>
                    </select>
                  </div> 
                  <div class="taches pb-50">
                    <h3 class="p-50"> Listes des différentes taches</h3>
                    <div class="date d-flex flex-row align-items-center justify-content-between">
                     
                    <div class="select-controltaches d-flex justify-content-between">
                      <select class="select "  name="entreprise">
                      <option value=""> Tâches </option>
                      <option value="1"> Nettoyage Serveur </option>
                      <option value="2"> dev  </option>
                      <option value="3">3  </option>
                      <option value="4"> 4 </option>
                      <option value="5"> 5 </option>
                      <option value="6"> 6 </option>
                      <option value="7"> 7 </option>
                      <option value="8"> 8 </option>
                     </select>
                     <button class="btn btn-primary d-flex flex-row align-items-center"><img class="icon" src="/src/assets/icons/plus.png " width="15"  alt=""> Ajouter Tâches</button>     
                   </div> 
                </div>
              </div>
              <h3 class="pt-50">Facturation</h3>
                
                <div class="select-controlwhite d-flex justify-content-end mb-50">
                    <label for="">Taux horaire</label>
                    <select name="entreprise">
                      <option value=""> 40€ </option>
                      <option value="1"> 30€ </option>
                      <option value="2"> 35€ </option>
                      <option value="3"> 45€  </option>
                      <option value="4"> 50€ </option>
                      </select>
                      
                  </div> 
                  <div class=" facturation d-flex flex-row align-items-center justify-content-end pb-50">
                   <div class="input-control">
                        <label for="">Total facturation</label>
                      <input type="text">
                    </div>
                  </div>
                  
                  
           </div>
           <div class="validation d-flex flex-row align-items-center justify-content-evenly">
                  <button class="btn btn-segondary">Annuler</button>
                  <button class="btn btn-primary ">Valider</button>
                  </div>
        </div>
        
</div>
</template>

<style lang="scss" scoped>

.modal{
        width:100%;
        height:1800px;
        background:rgba(0,0,0,0.5);
        z-index:10;
        position:absolute;
        top:0;
        left:0;
        padding-top:30px;
    }

    .modal__inner{
        max-width:60%;
        min-width:20%;
        padding:16px 32px 0px ;
        height:auto;
        margin:auto;
        background: var(--gray-1);
        border-radius: 4px;
    }

    h2, h4, h3{
        color: var(--text-segondary-color)
    }
    .icon{
  margin-right: 10px;
}
  
    .titre{
       padding-bottom: 80px;
       border-bottom: var(--border);
    }


h3{
  padding-left: 30px;
}
span{
    font-size: 16px;
}
input{
  margin-left: 30px;
  
}
select{
  margin-left: 30px;
  
}
.input-control{
    margin-left: 20px;
    display: flex;
    align-items: center;
    max-width: 450px;
    background-color: var(--gray-1);
    border-radius:6px;
    padding:10px 15px;
}

.input-control input{
    width: 100%;
    font-family: var(--font-family-);
    font-size:14px;
    padding: 5px 10px;
    outline: 0;
    border:#f9f9f9 solid 2px;
    color: var( --text-color);
    border-radius: 2px;
    background-color: #f4f4f4;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1)

}



.input-control ::placeholder{
    color: #838f9f;
    font-size: 14px;
}

.select-control{
    margin-left: 20px;
    display: flex;
    align-items: center;
    min-width: 300px;
    max-width: 450px;
    background-color: var(--gray-1);
    border-radius:6px;
    padding:10px 15px;
}

.select-control select{
    width: 100%;
    font-family: var(--font-family-);
    font-size:14px;
    padding: 5px 10px;
    outline: 0;
    border:#f9f9f9 solid 2px;
    color: white;
    border-radius: 2px;
    background-color: var(--second-1);
    box-shadow: 0 2px 10px rgba(0,0,0,0.1)

}
.select-controlwhite{
    width: 100%;
    margin-left: 20px;
    display: flex;
    align-items: center;
   
    background-color: var(--gray-1);
    border-radius:6px;
    padding: 5px 10px;
}

.select-controlwhite select{
    min-width: 300px;
    max-width: 450px;
    font-family: var(--font-family-);
    font-size:14px;
    padding: 5px 10px;
    outline: 0;
    border:#f9f9f9 solid 2px;
    color: var( --text-color);
    border-radius: 2px;
    background-color: #f4f4f4;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1)


}
.select-controltaches{
    width: 100%;
    margin-left: 20px;
    display: flex;
    align-items: center;
    
    background-color: var(--gray-1);
    border-radius:6px;
    padding:10px 15px;
}

.select-controltaches select{
    min-width: 300px;
    max-width: 450px;
    font-family: var(--font-family-);
    font-size:14px;
    padding: 5px 10px;
    outline: 0;
    border:#f9f9f9 solid 2px;
    color: var( --text-color);
    border-radius: 2px;
    background-color: #f4f4f4;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1)


}
option{
    background-color: white;
    color: var(--text-segondary-color)
}

textarea{
  border-radius: 4px;
  border: var(--border);
  width: 70%;
  height: 150px;
  padding: 15px 15px;
  font-family: var(--font-family-);
  
}

.date {
    margin-left: 20px;
    width: 100%;
    
    background-color: var(--gray-1);
    border-radius:6px;
    padding:10px 15px;
}
.date input {
    min-width: 300px;
    max-width: 450px;
    font-family: var(--font-family-);
    font-size:14px;
    padding: 5px 10px;
    outline: 0;
    border:#f9f9f9 solid 2px;
    color: var( --text-color);
    border-radius: 2px;
    background-color: #f4f4f4;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1)
}
 .taches{
  border-top: var(--border);
  border-bottom: var(--border);
 }
select.select{
  margin:0;
}

.validation{
  background: white;
  height: 80px;
  padding-right: 0px;
  border-top: 1px solid var(--second-1);
  border-left: 1px solid var(--second-1);
  border-right: 1px solid var(--second-1);
}
</style>