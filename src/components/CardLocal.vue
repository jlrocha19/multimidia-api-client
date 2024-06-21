<template>
  <div class="card">
    <p class="card-title">{{ anime.name }}</p>
    <ul class="card-description">
      <li>Nome: {{ anime.Nome }}</li>
      <li>Genero {{ anime.Genero }}</li>
      <li>Nota: {{ anime.Nota }}</li>
      <li>Temporadas: {{ anime.Temporadas }}</li>
      <li>Episodios: {{ anime.Episodios }}</li>
      <li>Descrição: {{ anime.Descrição }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "CardLocal",
  props: {
    anime: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style>
</style>