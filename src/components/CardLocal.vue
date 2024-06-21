<template>
  <div class="card">
    <p class="card-title">{{ anime.name }}</p>
    <ul class="card-description">
      <li>Altura: {{ anime.height }}</li>
      <li>Peso: {{ anime.mass }}</li>
      <li>Cor do cabelo: {{ anime.hair_color }}</li>
      <li>Cor de pele: {{ anime.skin_color }}</li>
      <li>Cor dos olhos: {{ anime.eye_color }}</li>
      <li>Ano: {{ anime.birth_year }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "CardLocal",
  props: {
    animes: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style>
</style>