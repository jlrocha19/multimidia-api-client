<template>
  <div>
    <h4 class="type">Cartões</h4>

    <div class="container">
      <div v-for="anime in animes" :key="anime.id">
        <card-local :anime="anime"></card-local>
      </div>
    </div>
  </div>
</template>

<script>
import CardLocal from "@/components/CardLocal.vue";

const API_URL = `http://localhost:3333/alunos`;

export default {
  data: () => ({
    animes: [],
  }),
  methods: {
    async getAnimes() {
      const response = await fetch(API_URL);
      const data = await response.json();

      this.people = data;
    },
  },
  created() {
    this.getAnimes();
  },
  components: {
    CardLocal,
  },
};
</script>