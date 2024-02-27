<template>
  <div class="home">
    <MainMovieCard></MainMovieCard>
    <SearchBox></SearchBox>
    <MoviesList></MoviesList>
    
  </div>
</template>

<script>
import MainMovieCard from '@/components/MainMovieCard.vue'
import SearchBox from '@/components/SearchBox.vue'
import MoviesList from '@/components/MoviesList.vue'
export default {
  components:{MainMovieCard, SearchBox, MoviesList}
};
</script>

<style scoped>

</style>
