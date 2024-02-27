<template>
<HeaderComponent></HeaderComponent>

<main>
  <router-view/>
</main>

<FooterComponent>
</FooterComponent>
  
</template>

<script>
import HeaderComponent from '@/components/HeaderComponent.vue'
import FooterComponent from '@/components/FooterComponent.vue'
export default {
  components:{ HeaderComponent, FooterComponent}
  
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Oswald:wght@200..700&display=swap');
body{
  background: #3f4969;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  height: auto;
  font-family: Oswald;
}


</style>
