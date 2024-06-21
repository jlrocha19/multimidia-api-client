<template>
  <div class="card">
    <p class="card-title">{{ person.name }}</p>
    <ul class="card-description">
      <li>Altura: {{ person.height }}</li>
      <li>Peso: {{ person.mass }}</li>
      <li>Cor do cabelo: {{ person.hair_color }}</li>
      <li>Cor de pele: {{ person.skin_color }}</li>
      <li>Cor dos olhos: {{ person.eye_color }}</li>
      <li>Ano: {{ person.birth_year }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    person: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style>
</style>