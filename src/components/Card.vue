<template>
  <div class="card mt-3 mb-3 w-100 shadow">
    <img :src="image" class="card-image rounded-bottom" alt="Cartão" />
    <div class="card-body text-center">
      <h5 class="card-title">{{nome}}</h5>
      <p class="card-text text-truncate">
        {{texto}}
      </p>
      <router-link :to="`/tema/${id}`" class="btn btn-outline-info rounded-pill w-100">Saiba mais</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props:[
      'image','nome','texto','id'
  ]
};
</script>

<style>
.card-image{
  height: 200px;
  object-fit: cover;
}

.card:hover{
  transform: scale(1.05);
}
</style>