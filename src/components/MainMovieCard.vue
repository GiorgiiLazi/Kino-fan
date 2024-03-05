<template>
  <div class="main-movie-card">
      <router-link :to="'/movie/' + 'tt2560078/'">
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
    </router-link>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.main-movie-card {
  display: block;
  position: relative;
  height: 500px;
  display: flex;
  justify-content: center;
  align-content: center;
  
  
}
.main-movie-card a{
  position: relative;
  height: 500px;
  display: flex;
  justify-content: center;
  align-content: center;
}
.featured-img {
  display: block;
  max-width: 300px;
  position: relative;
  z-index: 0;
}
.detail {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  
  background-color: rgba(0, 0, 0, 0.6);
  padding: 10px;
  z-index: 1;
  color:rgb(0, 216, 0);
  max-width: 280px;
  font-size: 20px;
  
}
.detail p{
  color: white
}
@media only screen and (max-width: 600px ){
  .detail {
    position: absolute;
    bottom: 0px;
  }
  .featured-img {
  max-width: 100%;;
  height: 500px;
  width: 100%;
  padding: 0;
  }
  .detail {
  max-width: 100%;
  font-size: 20px;
  }
}



</style>