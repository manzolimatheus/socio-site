<template>
  <footer class="text-center p-3">
      <span class="text-white">3ºETIM DESENVOLVIMENTO DE SISTEMAS | {{ActualYear}}</span>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  computed:{
    ActualYear: function(){
      const date = new Date;

      return date.getFullYear();
    }
  }
}
</script>

<style scoped>
footer{
  background-color: var(--theme-color);
}
</style>