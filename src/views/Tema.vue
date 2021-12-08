<template>
  <div>
    <div class="text-center vh-100 p-5" id="loading">
      <div
        class="spinner-border mt-lg-5"
        role="status"
        v-if="pageLoaded === false"
      ></div>
    </div>
    <div class="content" v-if="pageLoaded === true">
      <Banner :image="data[0].image" />
      <div class="container p-3 text-center">
        <h1>Movimento {{ data[0].nome }}</h1>
        <div class="row">
          <div class="col-lg">
            <img
              v-for="(ilustracao, index) in data[0].ilustracao"
              :key="index"
              :alt="`Ilustração do ${data[0].nome}`"
              :src="ilustracao"
              class="w-100 rounded mt-3"
            />
          </div>
          <div class="col-lg">
            <p class="texto">{{ data[0].texto }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Banner from "@/components/Banner.vue";

export default {
  name: "Tema",
  props: {
    id: {
      type: String,
    },
  },
  components: {
    Banner,
  },
  data() {
    return {
      data: [],
      pageLoaded: false,
    };
  },
  methods: {
    async LoadInfo() {
      const url = `https://socio-64ea.restdb.io/rest/temas?q={"_id":"${this.id}"}`;
      fetch(url, {
        headers: {
          "cache-control": "no-cache",
          "x-apikey": "61aec10f72a03f5dae822181",
        },
      })
        .then((response) => response.json())
        .then((data) => {
          this.data = data;
          this.pageLoaded = true;
          document.querySelector('#loading').style.display = 'none'
        });
    },
  },
  mounted() {
    this.LoadInfo();
  },
};
</script>

<style scoped>
</style>