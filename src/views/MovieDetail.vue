<template>
  <div class="movie-detail">
    <header>
      <div>
        <h2 class="movie-title">{{ movie.Title }}</h2>
        <h3 class="release">{{ movie.Released }}</h3>
      </div>
      <div class="rating-box">
        <p>IMDb Rating</p>

        <div class='ratings'>
          <p>
            <span class="material-symbols-outlined"> star_rate_half </span>
            {{ movie.imdbRating }}/10
          </p>
          <p class="votes">{{ movie.imdbVotes }} votes</p>
        </div>
      </div>
    </header>

    <main>
      <div class="poster">
        <img :src="movie.Poster" alt="poster" />
      </div>
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
        `http://www.omdbapi.com/?apikey=${env.apiKey}&i=${route.params.id}&plot=full`
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
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  margin: 5px;
  padding: 5px;
  font-size: 25px;
  color: #999
}
.material-symbols-outlined {
  color: darkgoldenrod;
  padding: 0;
  margin: 0;
  font-size: 25px;
  display: inline-block;
}
.ratings{
  display: flex;
  align-items:flex-end;
  justify-content: space-between;
}
.ratings p{
  font-size: 25px;
  padding: 8px;
}
.genre{
  color: #999
}
.plot{
  font-size: 20px;
}
</style>