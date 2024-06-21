<template>
<div class="icon"> 
    <img class="imgTelainicial" src="../assets/img/tela inicial.png" width="200" height="300"> 
  </div>
  
  <div class = "container mt-5 mb-5" id="app">
    
    <form @submit.prevent="fetchAnimes">
      <div class="form-group mt-5">
        <label class="mb-3 h2" for="animeInput" >Digite o nome do seu anime:</label>
        <input v-model="nome" type="text" class="form-control" id="animeInput" aria-describedby="emailHelp" placeholder="Seu anime">
      </div>
      <button type="submit" class="btn btn-primary mt-3">Enviar</button>
    </form>
    <div class="" v-if="loading">Carregando...</div>
    <div class="text-danger" v-else-if="error">Erro ao carregar os animes</div>
    <div v-else>
      <div class="d-flex bg-light p-3 border" v-for="anime in animes">
        <img :src="anime.images.jpg.image_url" :alt="anime.titles[0].title" />
        <p class="mr-auto p-3 text-success">{{anime.titles[0].title}}</p>
        
      </div>
    </div>
  </div>
</template>

<script>
export default {
      data() {
        return {
          nome: "",
          animes: [],
          loading: true,
          error: false,
         
        }
      },
      methods: {
        async fetchAnimes() {
          this.loading = true;
          this.error = false;
          const API_URL = `https://api.jikan.moe/v4/anime?q=${this.nome}&sfw`;

          if (this.nome.toLowerCase() === 'anime' || this.nome.toLowerCase() === 'hentai') {
              alert('Essa palavra não e permetida!');
              location.reload();
            }
            else{
                    //Axios é uma biblioteca JavaScript usada para fazer requisições HTTP
                    //ele ja converte para json automaticamente
              fetch(API_URL).then(async response => {//caso de certo ele então pega a resposta e insere no array de animes 
                  const json = await response.json();//response.data sempre será padrão
                  this.animes = json.data
                  this.animes = json.data
                }).catch(error => {
                  console.error(error);
                  this.error = true;
                }).finally(() => {
                  this.loading = false;
                });
            }
          

        }
      },
      created() {
        //this.fetchAnimes()
      }
    }

</script>

<style>
.icon{
    position:absolute; 
    margin-left: 1000px;
}
</style>