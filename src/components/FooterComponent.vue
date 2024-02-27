<template>
  <footer>
    <div>&#169; <span id='date'>{{date}}</span></div>
  </footer>
</template>

<script>
export default {
data() {
  return{
    date: new Date().getFullYear()
  }
}
}
</script>

<style scoped>
footer{
  padding: 0px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute; 
  bottom: 0; 
  left: 0;
  width: 100%;
  background-color: transparent;
  background-color: rgba(63, 171, 249, 0.1);
  font-weight: bold;
  font-family: Oswald;
  box-shadow: 0px -5px 6px rgba(0, 0, 0, 0.2);
}


footer div{
  padding: 0px;
  margin: 0px;
  color:rgb(0, 216, 0);
  margin: 0px 10px;
}


</style>