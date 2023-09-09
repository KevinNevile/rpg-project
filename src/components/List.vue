<script setup>
const classe = defineProps(["name", "url"])

</script>

<template>  
    <div class="col-3 mt-4 ">
        <div class="card mb-5">
        <img class="card-img-top" src="../assets/favicon.ico" alt="Card image cap">
            <div class="card-body mx-auto">
                <h5 class="card-title text-center capitalize">{{ classe.name }}</h5>

                <a :href="classe.url" target="_blank" class="btn btn-primary">Detalhes</a>
            </div>
        </div>
    </div>
</template>

<style> 
    .capitalize{
        text-transform: capitalize;
    }
</style>