<script setup>
import {ref} from 'vue'

let num = ref(0)

</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-dark border-bottom border-body " style="background-color: rgba(102, 0, 0, 0.863);">
    <div class="container-fluid">
      <img src="../src/assets/D20.svg" alt="Icone" width="30" height="30">
      <router-link to="/" class="navbar-brand">RPG-Races</router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span> 
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">

        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link to="/" class="nav-link" aria-current="page">Home</router-link>
          </li>  
          <!-- <li class="nav-item">
            <router-link to="/about" class="nav-link">About</router-link>
          </li> -->
        </ul>
      </div>
    </div>
  </nav>


  
  <div class="main mt-5 d-flex justify-content-center align-items-center col-md-12 bg-img bg-cover has-bg-img " style="background-image:url('../src/assets/StoneWall12.svg')">
    

    <router-view></router-view>
  </div>
</template>
