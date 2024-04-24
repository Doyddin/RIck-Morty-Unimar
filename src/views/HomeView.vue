<script setup>
import { onMounted, reactive, ref } from "vue";
import ListCharacters from "../components/ListCharacters.vue";

let characters = reactive(ref());

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character?page=1")
    .then((response) => response.json())
    .then((response) => {
      characters.value = response.results;
    })
})
</script>

<template>
  <div class="container">
    <div class="text-center">
      <h1>Listagem de Personagens de "Rick and Morty"</h1>
    </div>
    <div class="col-sm-12 col-md-12">
      <div class="card">
        <div class="card-body row">
          <ListCharacters v-for="c in characters" :key="c.name" :name="c.name" :status="c.status" :species="c.species"
            :gender="c.gender" :location="c.location" :image="c.image" :episode="c.episode" />
        </div>
      </div>
    </div>
  </div>
</template>
