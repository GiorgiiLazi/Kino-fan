<template>
  <div class="movie-detail">
    <header>
      <div>
      <h2 class='movie-title'>{{movie.Title}}</h2>
      <h3 class="release">{{movie.Released}}</h3>
    </div>
    <div class="rating-box">
      <p class='rating'>IMDB Rating: {{movie.imdbRating}}/10</p>
      <p class='votes'>{{movie.imdbVotes}} votes</p>
    </div>
    </header>

    <main>
      <div class="poster">
        <img :src="movie.Poster" alt="poster">
      </div>
      <div class="genre" >Genre: {{movie.Genre}}</div>
      <div class="plot">{{movie.Plot}}</div>
      <hr>
      <div class="director">Director: {{movie.Director}}</div>
      <hr>
      <div class="writer">Writer: {{movie.Writer}}</div>
      <hr>
      <div class="actors">Actors: {{movie.Actors}}</div>
    </main>
    
  </div>
</template>

<script>
import { ref, onBeforeMount} from "vue";
import { useRoute } from "vue-router";
import env from '@/env.js'
export default {
  setup() {
    const movie = ref({});
    const route = useRoute();
    

    onBeforeMount(() => {
      fetch(`http://www.omdbapi.com/?apikey=${env.apiKey}&i=${route.params.id}&plot=full`)
      .then(res => res.json())
      .then(data => movie.value = data)
      .catch(err => console.log(err))
    });

    return { movie, route };
  },
};
</script>

<style scoped>
.movie-detail{
  padding: 20px;
  color: white;
}
.movie-detail header{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.rating-box{
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.rating-box{
  margin: 5px;
  padding: 5px;
}
</style>