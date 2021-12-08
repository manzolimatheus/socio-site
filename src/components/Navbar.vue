<template>
  <nav class="nav">
    <router-link to="/">💭 Sociologia</router-link>
    <router-link to="/">Início</router-link>
    <li class="nav-item dropdown">
      <a
        class="dropdown-toggle"
        href="#"
        id="navbarDropdown"
        role="button"
        data-bs-toggle="dropdown"
        aria-expanded="false"
      >
        Movimentos
      </a>
      <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
        <li v-for="tema in temas" :key="tema._id">
          <router-link
            :to="{ name: 'Tema', params: { id: tema._id } }"
            class="dropdown-item text-dark"
            >{{ tema.nome }}</router-link
          >
        </li>
      </ul>
    </li>
  </nav>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      temas: [],
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
      });
  },
};
</script>

<style scoped>
nav {
  background-color: var(--theme-color);
  padding: 1%;
}

nav a {
  color: #ffffff;
  text-decoration: none;
  padding-inline: 3%;
}

nav a:hover {
  color: var(--white-hover);
}
</style>