<template>
  <form @submit.prevent class="search-box">
    <input class='text-input' type="text" name="" placeholder="What are you looking for?">
    <input id="submit" type="submit" value="Find movie">
  </form>
</template>

<script>
export default {

}
</script>

<style scoped>
.search-box{
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 16px;
}
input{
  display: black;
  appearance: none;
  border: none;
  outline: none;
  background: none;
}
.text-input{
  
  color: #FFF;
  background-color: #496583;
  font-size: 20px;
  padding: 10px 16px;
  border-radius: 8px;
  margin-bottom: 15px;
  transition: 0.4s
}
input ::placeholder{
  color: red
}
input :focus{
  box-shadow: 0px 3px 6px rgba(0,0,0,0.2)
}
</style>