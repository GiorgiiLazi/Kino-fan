<template>
  <div class="movie-detail">
    <header>
      <transition name="title" appear>
        <div>
          <h2 class="movie-title">{{ movie.Title }}</h2>
          <h3 class="release">{{ movie.Released }}</h3>
        </div>
      </transition>
      <transition name='rating' appear class="rating-box">
        <div>
          <p class="imdb">IMDb Rating</p>

        <div class='ratings'>
          <p>
            <span class="material-symbols-outlined"> star_rate_half </span>
          </p>
          <p class="votes">{{ movie.imdbRating }}/10 <br>
          {{ movie.imdbVotes }} votes</p>
        </div>
        </div>
        
      </transition>
    </header>

    <main>
      <transition appear name="poster" class="poster">
        <img :src="movie.Poster" alt="poster" />
      </transition>
      <div class="genre">Genre: {{ movie.Genre }}</div>
      <div class="plot">{{ movie.Plot }}</div>
      <hr />
      <div class="director">Director: {{ movie.Director }}</div>
      <hr />
      <div class="writer">Writer: {{ movie.Writer }}</div>
      <hr />
      <div class="actors">Actors: {{ movie.Actors }}</div>
    </main>
  </div>
</template>

<script>
import { ref, onBeforeMount } from "vue";
import { useRoute } from "vue-router";
import env from "@/env.js";
export default {
  setup() {
    const movie = ref({});
    const route = useRoute();

    onBeforeMount(() => {
      fetch(
        `https://www.omdbapi.com/?apikey=${env.apiKey}&i=${route.params.id}&plot=full`
      )
        .then((res) => res.json())
        .then((data) => (movie.value = data))
        .catch((err) => console.log(err));
    });

    return { movie, route };
  },
};
</script>

<style scoped>
.movie-detail {
  padding: 20px;
  color: white;
  margin-bottom: 100px;
}

.movie-detail header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  text-transform:uppercase;
}
.rating-box {
  width: 30%;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 5px;
  padding: 5px;
  font-size: 20px;
  color: #999
}
.material-symbols-outlined {
  color: darkgoldenrod;
  padding: 0;
  margin: 0;
  font-size: 35px;
  display: inline-block;
}
.ratings{
  display: flex;
  align-items:flex-start;
  justify-content: flex-start;
  justify-content: space-between;
}
.ratings p{
  font-size: 20px;
  padding: 0px 5px 0px 5px;
}
.genre{
  color: #999;
  margin-bottom: 20px;
}
.plot{
  font-size: 20px;
}
.imdb{
  align-self: center;
}

.title-enter-from, .poster-enter-from{
  opacity: 0;
  transform: translateX(-300px)
}
.title-enter-to, .poster-enter-to{
  opacity: 1;
  transform: translateYX(0px)
}
.title-enter-active, .poster-enter-active{
  transition: all 2s ease
}
.rating-enter-from{
  opacity: 0;
  transform: translateX(300px)
}
.rating-enter-to{
  opacity: 1;
  transform: translateX(0px)
}
.rating-enter-active{
  transition: all 2s ease
}
</style>