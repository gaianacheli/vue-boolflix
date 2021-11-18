<template>
    <div class="searchbox flex">
      <input @keyup.enter="$emit('search',searchMovies)" class="bar" v-model="searchMovies" type="search" placeholder="Cerca un film">
      <button  @click="$emit(`search`, searchMovies)">Search</button>

    </div>
</template>


<script>
export default {
    
    data(){
        return{
           searchMovies: "",  
        }
    },
}
</script>
