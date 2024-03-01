<template>
  <div class="movies-list">
    <div v-for="movieItem in movieList" class="movie" :key="movieItem.imdbID">
      <router-link 
      :to="'/movie/' + movieItem.imdbID"
      class="movie-link">
      <div class="product-image">
        <img :src="movieItem.Poster" :alt="movieItem.Title">
        <div class="type">{{movieItem.Type}}</div>
      </div>
      <div class="detail">
        <p class='year'>{{movieItem.Year}}</p>
        <h3 class="movie-title">{{movieItem.Title}}</h3>
      </div>
      </router-link>
      
    </div>
  </div>
</template>

<script>
import { computed } from 'vue'
export default {
  props:['movies'],
  setup(props){
    const movieList = computed(() =>{
      return props.movies
    })

    return {movieList}
  }


}
</script>

<style>
.movies-list{
  display: flex;
  flex-wrap: wrap;
  margin: 0px 10px;
}
.movie{
  max-width: 50%;
  flex: 1 1 40%;
  padding: 16px 8px;;
}
.movie-link{
  display: flex;
  flex-direction: column;
  height: 100%;
}
.product-image{
  position: relative;
  display: block;
}
.product-image img{
  display: block;
  width: 100%;
  height: 275px;
  object-fit: cover
}
.type{
  position: absolute;
  bottom: 16px;
  padding: 8px;
  left: 0px;
  background-color: #42Bb83;
  text-transform: capitalize;
  color: white;
  border-radius: 0px 4px 4px 0px;
}
.detail{
  background-color:#496583;
  padding: 16px 8px;
  flex: 1 1 100%;
  border-radius: 0px 0px 8px 8px;
}
.year{
  text-decoration: none;
  color: #AAA;
  font-size: 15px;
}
.movie-title{
  color: white;
  font-weight: 24px;
}
a {
text-decoration: none;
}

@media only screen and (min-width: 600px){
  .movie{
  max-width: 20%;
  flex: 1 20%;
  padding: 16px 8px;
  }
  .product-image img{
  display: block;
  width: 100%;
  height: 300px;
  object-fit: cover
  }
  
}


</style>