<script setup>
const classe = defineProps(["name", "url"])

</script>

<template>  
    <div class="col-3 mt-5 ">
        <div class="card mb-3">
        <img class="card-img-top" src="../assets/favicon.ico" alt="Card image cap">
            <div class="card-body mx-auto">
                <h5 class="card-title text-center capitalize">{{ classe.name }}</h5>
                <a :href="'https://www.dnd5eapi.co/api/classes/' + classe.url" target="_blank" class="btn btn-primary">Detalhes</a>
            </div>
        </div>
    </div>
</template>

<style> 
    .capitalize{
        text-transform: capitalize;
    }
</style>