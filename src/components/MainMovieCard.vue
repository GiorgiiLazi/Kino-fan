<template>
  <div class="main-movie-card">
      <router-link to="movie/tt2560078"></router-link>
      <img
        class="featured-img"
        src="https://m.media-amazon.com/images/M/MV5BN2FmYmM1ODctNjkzNC00MzcyLTkyOWYtZmZjNjY2ZmU3MmI3XkEyXkFqcGdeQXVyODk4OTc3MTY@._V1_FMjpg_UX1000_.jpg"
        alt="Boston Strangler Poster"
      />
      <div class="detail">
        <h3 class="featured-title">Boston Strangler</h3>
        <p>
          Loretta McLaughlin was the reporter who first connected the murders
          and broke the story of the Boston Strangler.
        </p>
      </div>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.main-movie-card {
  position: relative;
  
}
.featured-img {
  display: flex;
  display: block;
  height: 500px;
  width: 100%;
  object-fit:cover;
  
  

  position: relative;
  z-index: 0;
}
.detail {
  position: absolute;
  align-content: end;
  left: 0;
  bottom: 0px;
  background-color: rgba(0, 0, 0, 0.6);
  padding: 16px;
  z-index: 1;
  color:rgb(0, 216, 0);
  width: 100%;
  font-size: 20px;
  
}
.detail p{
  color: white
}



</style>