<script>
import List from '../components/List.vue';

export default {
  setup() {
    const racas = ref([]); // Inicialize a variável reativa para armazenar os dados da equipe
    
    onMounted(() => {
      const urlParams = new URLSearchParams(window.location.search);
      const url = urlParams.get('races');

      // Certifique-se de que "race" seja definido antes de fazer a chamada da API
      if (url) {
        // Realize a chamada da API somente quando houver um "race" válido
        fetch("https://www.dnd5eapi.co/api/races/" + url)
          .then(response => response.json())
          .then(response => {
            racas.value = response;
            console.log(racas.value);
          })
          .catch(error => {
            console.error("Erro na chamada da API:", error);
          });
      } else {
        console.error("Race inválido ou ausente na URL");
      }
    });

    return {
      racas
    };
  }
};
</script>

<template>
    <ul>
        <li class="list-group-item shadow-sm p-2 mb-3 bg-white rounded border-top-0">
            <h3 class="text-primary">Alignment:</h3> {{ racas.speed }}
        </li>
    </ul>
</template>
