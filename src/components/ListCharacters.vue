<script setup>
const character = defineProps(["name", "status", "species", "gender", "location", "image", "episode"])
</script>

<template>
    <div class="col-md-4 g-3">
        <div class="card m-3 p-2">
            <img :src="character.image" class="card-img-top" alt="..." height="80" />
            <div class="card-body">
                <div class="flex-column g-3">
                    <p class="fw-bold text-center">
                        {{ character.name }}
                    </p>
                    <p>
                        Status: {{ character.status }}
                    </p>
                    <p>
                        Espécie: {{ character.species }}
                    </p>
                    <p>
                        Gênero: {{ character.gender }}
                    </p>
                    <p>
                        Localização Atual: {{ character.location.name }}
                    </p>
                    <p>
                        Apareceu em {{ character.episode.length }} episódios
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
</style>