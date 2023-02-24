<script setup lang="ts"></script>

<template>
  <div>
    <nav class="side-nav">
            <div class="nav-logo">
                <div class="logo">
                    <img src="../assets/icons/hombre.png" span class="logo-1" alt="">
                    
                </div>  
            </div>

            <a href="#" class="block-link">
                <img src="../assets/icons/dashboard.png" alt="">
                <span class="nav-links">Dashboard</span>
                
            </a>
            <div class="fill"></div>
            <a href="#" class="block-link ">
                <img src="../assets/icons/customer.png">
                <span class="nav-links">Missions</span>
                
            </a>
            <div class="fill"></div>
            <a href="#" class="block-link">
                <img src="../assets/icons/tax.png">
                <span class="nav-links">Factures</span>
                
            </a>
            <div class="fill"></div>
            <a href="#" class="block-link">
                <img src="../assets/icons/invoice.png">
                <span class="nav-links">Devis</span>
               
            </a>
            <div class="fill"></div>
            <a href="#" class="block-link">
                <img src="../assets/icons/google-calendar.png">
                <span class="nav-links">Agenda</span>
               
            </a>
        </nav>
  </div>
</template>

<style lang="scss" scoped>
.side-nav{
    position:relative; /*position fixed tjts par rapport au body*/
    display: flex; 
    flex-direction: column;
    width:100%;
    height: 100%;
    border-right:1px solid #bdbdbd;
    background: linear-gradient(to right, var(--primary-1), #14819c);
    color:white;
    
}
 .nav-logo{
    width:100%;
    margin: auto;
    display:flex;
    justify-content: center; 
    cursor: pointer;
    margin: 50px auto;
    // padding: 60px;
    // border-radius: 999px;
    // background: var(--second-1);
   
 }

 .logo{
   display: flex;
    background: var(--second-1);
    width:120px;
    height: 120px;
    margin:auto;
    border-radius:999px;
    border: 5px solid var(--second-1)
 }
 .logo-1{
   display: flex;
    background: var(--second-1);
    width:100%;
    height: 100%;
    margin:auto;
    border-radius:999px;
    border: 1px solid var(--second-1)
 }


 .logo img{
    
    width:60%;
    margin: auto;
  

 }
.block-link{
    display:flex;
    color: white;
    text-decoration: none;
    padding: 20px 30px;
    font-weight: 500;
}

.block-link:hover{
    color:var(--second-1)
}

.block-link img {
    width:20px;
    color:white;
}

.nav-links{
    margin-left: 14px;
}

.fill{

    width:80%;
    height: 2px;
    background: rgb(57, 57, 57, 0.3);
    margin: 10px auto;
}

</style>