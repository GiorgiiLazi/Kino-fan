<template>
<header class="returnHome">
  <router-link id="linkHome" to="/">
    <span>Kino</span>Fan
  </router-link>
</header>
</template>

<script>
export default {

}
</script>

<style scoped>
.returnHome{
  position:sticky;
  top: 0px;
  width: 100%;
  padding: 0px;
  background-color: transparent;
  display:flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0px 5px 6px rgba(0, 0, 0, 0.2);
  z-index: 2;
  
}
#linkHome{
  text-decoration: none;
  font-size: 30px;
  font-weight: bold;
  font-family: Oswald;
  color: white;
  padding: 10px 20px;
  
}
#linkHome span{
  font-size: bolder;
  color:rgb(0, 216, 0)
}

</style>