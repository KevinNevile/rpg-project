<script setup>
import { onMounted, reactive, ref } from 'vue';
import List from '../components/List.vue';

let classes = reactive(ref());

onMounted(() => {
  fetch("https://www.dnd5eapi.co/api/classes/")
  .then(response => response.json())
  .then(response => {
    classes.value = response.results;
    console.log(response);
  })
}) 

</script>

<template>

  <!-- <main>
    <div class="container">
      <div class="row mt-4" style="background-color: brown;">
        <div class="col-sm-12 col-md-6">
          <div class="card" style="width: 18rem;">
            <img src="../assets/favicon.ico" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">teste</h5>
              <p class="card-text">teste</p>
            </div>
          </div>
        </div>
        <div class="col-sm-10 col-md-4"></div>
          <div class="card">
            <div class="card-body row">
              <List
              v-for="classe in classes"
              :key="classe.name"
              :name="classe.name"
              :url="classe.url"
              />
            </div>
          </div>
      </div>
    </div>
  </main> -->

  <!-- <main>
      <div class="row mx-auto">
        <div class="col-sm-12 col-md-6">
          <div class="card" style="width: 18rem;">
            <img src="../assets/favicon.ico" class="card-img-top" alt="...">
            <div class="card-body">
              <h5 class="card-title">teste</h5>
              <p class="card-text">teste</p>
            </div>
          </div>
        </div>
            <div class="card-body row mx-auto">
              <List
              v-for="classe in classes"
              :key="classe.name"
              :name="classe.name"
              :url="classe.url"
              />
            </div>
      </div>
  </main> -->

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
              v-for="classe in classes"
              :key="classe.name"
              :name="classe.name"
              :url="classe.index"
              />
            </div>
      </div>
    </div>
  </main>

</template>

