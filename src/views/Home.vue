<template>
  <div class="home">
    <div class="text-center vh-100 mx-auto p-5" id="loading">
      <div
        class="spinner-border text-center mt-lg-5"
        role="status"
        v-if="pageLoaded === false"
      >
        <span class="visually-hidden">Loading...</span>
      </div>
    </div>
    <div class="content" v-show="pageLoaded">
      <h1 class="text-center p-3">Os movimentos sociais</h1>
      <div class="container">
        <div class="row w-100 mx-auto">
          <div class="col-md-4" v-for="tema in temas" :key="tema._id">
            <Card
              :nome="tema.nome"
              :image="tema.image"
              :texto="tema.texto"
              :id="tema._id"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Card from "@/components/Card.vue";

export default {
  name: "Home",
  components: {
    Card,
  },
  data() {
    return {
      temas: [],
      pageLoaded: false,
    };
  },
  mounted() {
    const url = "https://socio-64ea.restdb.io/rest/temas";

    fetch(url, {
      headers: {
        "cache-control": "no-cache",
        "x-apikey": "61aec10f72a03f5dae822181	",
      },
    })
      .then((response) => response.json())
      .then((data) => {
        this.temas = data;
        this.pageLoaded = true;
        document.querySelector('#loading').style.display = 'none'
      });
  }
};
</script>
