<template>
  <div id="app">
    
    <NavBar></NavBar>
    <div class="row row-cols-1 row-cols-md-2 g-4">
        <CardComponent class="col"  v-for="movie in movies" v-bind:key="movie.id" v-bind:amovie="movie"></CardComponent>
    </div>
  
  </div>
</template>

<script>
import 'bootstrap'
import 'bootstrap/dist/css/bootstrap.min.css'
import CardComponent from './components/CardComponent.vue';
import NavBar from './components/NavBar.vue'
import axios from 'axios'
export default {
  name: 'App',
  components: {
    NavBar,
    CardComponent
  },
  data(){
    return{
      movies:[]
    }
  },
  mounted(){
    axios
    .get('https://api.themoviedb.org/3/movie/now_playing?api_key=df78dbf203b1cd1f3a6d506adc95f2fd&language=en-US&page=1')
    .then((response) => {
      this.movies = response.data.results.slice(0,4);
    })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 0px;
}
</style>