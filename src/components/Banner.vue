<template>
  <div id="banner">
      <img :src="image" alt="Banner" class="w-100 banner">
  </div>
</template>

<script>
export default {
    name: 'Banner',
    props:{
        image: {
            type: String
        }
    }
}
</script>

<style>
 .banner{
     height: 500px;
     object-fit: cover;
 }
</style>