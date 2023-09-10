<script setup>
const race = defineProps(["name", "url", "alig"])

</script>

<template>  
    <div class="col-3 mt-5 ">
        <div class="card mb-3">
        <img class="card-img-top" src="..." alt="Card image cap">
            <div class="card-body mx-auto">
                <h5 class="card-title text-center capitalize">{{ race.name }}</h5>
                <p class="card-text">{{ race.alig }}</p>
                <a :href="'https://www.dnd5eapi.co/api/races/' + race.url" target="_blank" class="btn btn-primary">Detalhes</a>
            </div>
        </div>
    </div>
</template>

<style> 
    .capitalize{
        text-transform: capitalize;
    }
</style>