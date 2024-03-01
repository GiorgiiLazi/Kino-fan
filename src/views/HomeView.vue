<template>
  <div class="home">
    <MainMovieCard></MainMovieCard>
    <SearchBox></SearchBox>
    
    
  </div>
</template>

<script>
import MainMovieCard from '@/components/MainMovieCard.vue'
import SearchBox from '@/components/SearchBox.vue'
export default {
  components:{MainMovieCard, SearchBox, }
};
</script>

<style scoped>

</style>
