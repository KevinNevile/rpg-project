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
      <div class="row mx-auto">
        <div class="col-sm-12 col-md-6">
          <div class="card mt-5 mb-5" style="width: 24rem;">
            <img src="../assets/favicon.ico" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">teste</h5>
              <p class="card-text">teste</p>
            </div>
          </div>
        </div>
            <div class="card-body row mx-auto">
              <List
              v-for="race in races"
              :key="race.name"
              :name="race.name"
              :url="race.index"
              :alig="race.alignment"
              />
            </div>
      </div>
    </div>
  </main>
</template>

