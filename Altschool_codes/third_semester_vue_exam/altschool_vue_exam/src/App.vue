<script setup>
import {RouterLink, RouterView} from 'vue-router';
import Sidebar from './components/Sidebar.vue';
</script>

<template>
  
  <nav>
    <RouterLink to="/" class="btn btn-primary ">Home</RouterLink>
    <RouterLink to="/repo" class="btn btn-primary ">Git Repos</RouterLink>
    <RouterLink to="/contact" class="btn btn-primary ">Contact</RouterLink>
    
    
  </nav>

  <main>
    <RouterView/>
  </main>
  <footer>
    <p>Copyright 2023.</p> 
  </footer>
</template>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Georgia, 'Times New Roman', Times, serif;

}
nav{
  display: flex;
  width: 100%;
  align-items: center;
  margin: auto;
  padding: 1.3rem;
  justify-content: space-around;
}
nav a{
  text-decoration: none;
  color: #242924;

  font-size: 30px;
  font-weight: 300;
  
}
nav img{
  width: 40px;
  height: 40px;
}

footer{
  position: fixed;
  bottom: 0;
  background-color: black;
  text-align: center;
  width: 100%;
  height: 40px;
  color: white;
}


</style>
