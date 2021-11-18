<template>
 <div class="sitemain">
   <SearchBox @search='search'/>
    <div class="container_movies flex">
     <div class="movie flex" v-for="movie in movies" :key="movie.id">
        <Movie
        :title="movie.title"
        :original_title="movie.original_title"
        :original_language="movie.original_language"
        :vote_average="movie.vote_average"/>
      </div>
    </div>
 </div> 
</template>

<script>
import Movie from './Movie.vue'
import axios from 'axios';
import SearchBox from './SearchBox.vue';
export default {
    components:{
        Movie,
        SearchBox,
    },
    data(){
    return{
        movies:[],
    }
  },
  methods:{
    search(searchMovies){
       this.callApi(searchMovies);
    
    },
       callApi(searchMovies){
      let API_URL= "https://api.themoviedb.org/3/search/movie?api_key=4db7aa0aef6b2145477778558e1489b1&language=it-IT&query="+ searchMovies +"&page=1"

      axios
      .get(API_URL)
      .then((response)=>{
        this.movies=response.data.results;
        console.log(this.movies);
      })
    },
  }
}
</script>

<style scoped lang="scss">
.searchbox{
  justify-content: center;
  margin-top: 2rem;
}
.container_movies{
 flex-wrap: wrap;
 justify-content: space-around;
}
.movie {
  padding: 10px;
}
</style>