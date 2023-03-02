<script setup lang="ts">
// import{ref} from 'vue'
//  const bbn = ref(false);


</script>

<template>
  <header>
    <div class="header-box px-20 d-flex flex-row align-items-center">
      <div class="input d-flex flex-row flex-fill align-items-center" >
        <a href="#" class="block-header d-flex flex-row ">
                <img src="../assets/icons/collapse.png" alt="" > 
                <h3>Missions</h3>
        </a>
        <div class="input-control">
                <label for="search">
                    <img src="../assets/icons/search.svg" alt="" >
                </label>
                <input type="text" id="search" placeholder="Recherche">
        </div>
      </div>
      <div class="date-control d-flex flex-row align-items-center mr-20">
         <input class="date mr-20" type="month" id="search" placeholder="Recherche">
         <img src="../assets/icons/settings.png" alt="">
      </div>
                
    </div>
  </header>
</template>

<style lang="scss" scoped>
.header-box{
    height: 100%;
    background: linear-gradient(to right, var(--primary-3), var(--primary-4)) 
}

a{
  color: white;
}
.input{
  justify-content: flex-start;
  margin-left:15%;
}
img{
  width:25px;
}
 h3{
  padding-left: 30px;
}
input{
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

.input-control img{
    width: 25px;
    position: relative;
    top: 2px;
    padding: 0 2px;
    
    
}
.input-control input{
    width: 100%;
    font-family: var(--font-family-);
    font-size:16px;
    padding-left: 10px;
    outline: 0;
    border:#f9f9f9 solid 2px;
    color: var( --text-color);
    background-color: #f4f4f4;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1)

}

.input-control ::placeholder{
    color: #838f9f;
    font-size: 16px;
}
 .date{
   
    font-size:16px;
    padding: 2px 5px 2px 10px;
    border-radius: 4px;
    
    border:#f9f9f9 solid 2px;
    color: var( --text-color);
    background-color: #f4f4f4;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1)
    
 }
 .date1{
   
    font-size:30px;
    padding: 2px 5px 2px 10px;
    border-radius: 4px;
    
    border:#f9f9f9 solid 2px;
    color: var( --text-color);
    background-color: #f4f4f4;
    box-shadow: 0 2px 10px rgba(0,0,0,0.1)
    
 }
</style>