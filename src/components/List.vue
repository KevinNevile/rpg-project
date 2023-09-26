<script setup>
import { ref, onMounted } from 'vue';

const race = defineProps(["name", "url", "speed"])
const imageUrl = `../src/assets/races/${race.url}.png`
const raceDetails = ref({});

const fetchRaceDetails = () => {
  fetch(`https://www.dnd5eapi.co/api/races/${race.url}`)
    .then(response => response.json())
    .then(data => {
      raceDetails.value = data;
      console.log(raceDetails.value);
    });
};

onMounted(fetchRaceDetails);

</script>

<template>  
    <div class="col-3 mt-5 ">
        <div class="card mb-3">
        <img class="card-img-top" :src="imageUrl" alt="Card image cap" >
            <div class="card-body mx-auto">
                <h5 class="card-title text-center capitalize">{{ race.name }}</h5>
                <a :href="'https://www.dnd5eapi.co/api/races/' + race.url" target="_blank" class="btn btn-success" data-bs-toggle="modal" :data-bs-target="'#raceModal-' + race.url">Detalhes</a>
            </div>
        </div>
    </div>

    <div class="modal fade" :id="'raceModal-' + race.url" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="raceModalLabel">Detalhes sobre a Raça: {{ race.name }}</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    <h5>Alignment:</h5> {{ raceDetails.alignment }}
                    <h5>Age:</h5> {{ raceDetails.age }}
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Fechar</button>
                </div>
            </div>
        </div>
    </div>



</template>

<style> 
    .capitalize{
        text-transform: capitalize;
    }
</style>