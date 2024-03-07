<template>
  <form @submit.prevent="SearchMovies()" class="search-box">
    <input 
    class='text-input'
    v-model="search"
    type="text"
    placeholder="What are you looking for?">
    
    <input id="submit" type="submit" value="Search">
  </form>
  <MoviesList :movies="movies"></MoviesList>
</template>

<script>
import { ref } from 'vue'
import env from '@/env.js'
import MoviesList from '@/components/MoviesList.vue'
export default {
  components:{MoviesList},
  setup(){
    const search = ref('')
    const movies = ref([])

    const SearchMovies = () =>{
      if(search.value != ''){
        fetch(`https://www.omdbapi.com/?apikey=${env.apiKey}&s=${search.value.trim()}`)
        .then(res => res.json())
        .then(data => { 
          movies.value = data.Search
          search.value = ''
          })
        .catch(err => console.log(err))
      }
    }

    return{
      search,
      movies,
      SearchMovies
    }
  }

}
</script>

<style scoped>
.search-box{
  display: flex;
  align-content: center;
  justify-content: center;

  flex-direction: column;
  padding: 16px;
  margin: 20px 0px 150px 0px;;
}
.search-box :focus{
  box-shadow: 0px 3px 6px rgba(0,0,0,0.3)
}
input{
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
input::placeholder{
  color: #f3f3f3
}
input :focus{
  box-shadow: 0px 3px 6px rgba(0,0,0,0.2)
}
#submit{
  margin: auto;
  display: block;
  max-width: 100%;
  width: 300px;
 
  background-color: #42Bb83;
  color: white;
  border-radius: 4px;
  padding: 16px;
  font-size: 20px;
  text-transform:uppercase;
  transition: 0.4s;
}
#submit:active{
  background-color: #3B8070;
}
</style>