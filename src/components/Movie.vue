<template>
<div class="cotainer">
     <div class="card flex">
        <p>TITOLO: {{title}}</p>
        <p>TITOLO ORIGINALE: {{original_title}}</p>
        <p>LINGUA ORIGINAE: {{original_language}}</p>
        <country-flag :country='original_language' size='small'/>
        <p>VOTO:{{vote_average}}</p>
     </div>
</div>

</template>


<script>
export default {
    name:'Movie',
    props: {
        title: String,
        original_title: String,
        original_language: String,
        vote_average: Number,
    },
  
}
</script>

<style scoped lang="scss">
.card{
    flex-direction: column;
    justify-content: space-around;
    border: 1px solid black;
    padding: 1rem;
}

</style>