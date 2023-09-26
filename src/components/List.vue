<script setup>
const race = defineProps(["name", "url", "speed"])
const imageUrl = `../src/assets/races/${race.url}.png`

</script>

<template>  
    <div class="col-3 mt-5 ">
        <div class="card mb-3">
        <img class="card-img-top" :src="imageUrl" alt="Card image cap" >
            <div class="card-body mx-auto">
                <h5 class="card-title text-center capitalize">{{ race.name }}</h5>
                <a :href="'https://www.dnd5eapi.co/api/races/' + race.url" target="_blank" class="btn btn-success">Detalhes</a>
            </div>
        </div>
    </div>


    <!-- data-bs-toggle="modal" data-bs-target="#exampleModal" -->
    <!-- <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
        <div class="modal-dialog">
            <div class="modal-content">
                <div class="modal-header">
                    <h5 class="modal-title" id="exampleModalLabel">Detalhes sobre a Raça</h5>
                    <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                </div>
                <div class="modal-body">
                    <p></p>
                </div>
                <div class="modal-footer">
                    <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                </div>
            </div>
        </div>
    </div> -->



</template>

<style> 
    .capitalize{
        text-transform: capitalize;
    }
</style>