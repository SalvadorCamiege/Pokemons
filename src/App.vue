<script setup>
import { ref } from 'vue';
import router from './router';

let num = ref(0); // Cria uma referência reativa
</script>

<template>
   <!-- NavBar -->
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
     <div class="container-fluid">
            <Router-Link class="navbar-brand" to="/">
            <img src="https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/3.png" alt="" width="50"    height="30"  class="d-inline-block align-text-top">
             Pokédex
            </Router-Link>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse"              data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                  <ul class="navbar-nav">
                        <li class="nav-item">
                              <Router-Link class="nav-link" aria-current="page" to="/">Home</Router-Link>
                        </li>
                        <li class="nav-item">
                              <Router-Link class="nav-link" to="/About">About</Router-Link>
                        </li>
                  </ul>
            </div>
      </div>
  </nav>
  <!-- contente -->
   <div class="main">
        <router-view></router-view>
   </div>

   <footer class="bg-primary text-light">
         <div>
            <p> APP Desenvolvido por <strong>Salvador Camiege</strong> {{ new Date().getFullYear()}}</p>
         </div>
   </footer>
</template>

<style>
       body{
          height: 100vh;
          background: rgb(2,0,36);
          background: linear-gradient(90deg, rgba(2,0,36,1) 1%, rgba(19,66,218,0.5242471988795518) 37%, rgba(0,212,255,1) 100%);
       }
       footer{
          position: fixed;
          bottom: 0;
          width: 100%;
          display: flex;
          align-items: center;
          justify-content: center;
          height: 56px;
       }
</style>


