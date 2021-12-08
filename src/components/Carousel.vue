<template>
  <div
    id="carouselExampleCaptions"
    class="carousel slide"
    data-bs-ride="carousel"
  >
    <div class="carousel-indicators">
      <button
        type="button"
        data-bs-target="#carouselExampleCaptions"
        data-bs-slide-to="0"
        class="active"
        aria-current="true"
        aria-label="Slide 1"
      ></button>
      <button
        type="button"
        data-bs-target="#carouselExampleCaptions"
        data-bs-slide-to="1"
        aria-label="Slide 2"
      ></button>
      <button
        type="button"
        data-bs-target="#carouselExampleCaptions"
        data-bs-slide-to="2"
        aria-label="Slide 3"
      ></button>
    </div>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img src="https://cafecomsociologia.com/wp-content/uploads/2018/03/tipos-de-movimentos-sociais-1024x594-1024x594.jpg" class="d-block w-100 carousel-image" alt="..." />
        <div class="carousel-caption d-none d-md-block">
          <h5>Tudo sobre os movimentos sociais</h5>
          <p>Conheça e aprenda sobre os movimentos que fizeram parte de nosso história.</p>
        </div>
      </div>
      <div class="carousel-item" v-for="item in items" :key="item.id">
        <img :src="item.image" class="d-block w-100 carousel-image" alt="Imagem em destaque" />
        <div class="carousel-caption d-none d-md-block">
          <h5>{{item.nome}}</h5>
          <span class="text-truncate">{{item.texto.substring(0,100)}}...</span>
        </div>
      </div>
    </div>
    <button
      class="carousel-control-prev"
      type="button"
      data-bs-target="#carouselExampleCaptions"
      data-bs-slide="prev"
    >
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Previous</span>
    </button>
    <button
      class="carousel-control-next"
      type="button"
      data-bs-target="#carouselExampleCaptions"
      data-bs-slide="next"
    >
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="visually-hidden">Next</span>
    </button>
  </div>
</template>

<script>
export default {
  name: "Carousel",
  props: ['items'],
}
</script>

<style>
.carousel-image{
    height: 500px;
    object-fit: cover;
    filter: brightness(0.3);
}
</style>