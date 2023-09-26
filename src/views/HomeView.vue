<script setup>
import { onMounted, reactive, ref } from 'vue';
import List from '../components/List.vue';

let races = reactive(ref());

onMounted(() => {
  fetch("https://www.dnd5eapi.co/api/races/")
  .then(response => response.json())
  .then(response => {
    races.value = response.results;
    console.log(response);
  })
}) 

</script>

<template>
  <main>
    <div class="container mb-5">
      <div class="row mx-auto col d-flex justify-content-center">
        <div class="col-sm-12 col-md-6">
          <div class="card mt-5 mb-5">
            <img src="../assets/Map.jpg" class="card-img-top" alt="...">
            <div class="card-body">
              <h2 class="card-title text-center">Bem vindo, Jogador!</h2>
              <h5 class="card-text text-center">Entenda melhor qual raça se encaixa com sua definição de personagem para começar a jogar!</h5>
            </div>
          </div>
        </div>
            <div class="card-body row mx-auto">
              <List
              v-for="race in races"
              :key="race.name"
              :name="race.name"
              :url="race.index"
              />
            </div>
      </div>
    </div>
  </main>
</template>

