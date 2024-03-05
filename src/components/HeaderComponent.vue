<template>
<transition tag="header" name="header" appear class="returnHome">
  <router-link id="linkHome" to="/">
    <span>Kino</span>Fan
  </router-link>
</transition>
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
.header-enter-from{
  opacity: 0;
  transform: scale(0.5);
  transform: translateX(200px)
}
.header-enter-to{
  opacity: 1;
  transform: scale(1);
  transform: translateX(0)
}
.header-enter-active{
 transition: all 2s ease
}

</style>