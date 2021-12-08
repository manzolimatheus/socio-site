<template>
  <Navbar/>
  <router-view :key="$route.params.id"/>
  <Footer/>
</template>


<script>

import Navbar from '@/components/Navbar'
import Footer from '@/components/Footer'

export default {
  components:{
    Navbar,
    Footer
  }
}
</script>

<style>

@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');

*{
  margin: 0;
  padding: 0;
  font-family: 'Roboto', sans-serif;
  --theme-color: black;
  --white-hover: #6ae1ff;
}

/* Scrollbar */
/* width */
::-webkit-scrollbar {
  width: 10px;
}
/* Track */
::-webkit-scrollbar-track {
  background: #f1f1f1;
}
/* Handle */
::-webkit-scrollbar-thumb {
  background: rgb(187, 187, 187);
  border-radius: 10px;
}
/* Handle on hover */
::-webkit-scrollbar-thumb:hover {
  background: #555;
}

.texto{
white-space: pre-line;
text-align: justify; 
}
</style>
