<template>
       <section class="container">

<ul class="nav justify-content-center">
             <li class="nav-item" v-for="(source, index) in sources" :key="index"><a class="nav-link" href="#">{{ source.names }}</a></li>
</ul>
       
       
<hr>

  </section>
  </template>

<script>


export default {
    data(){
        return{
   sources:[
       {names: 'US',sources: ['bloomberg','bbc-news','abc-news']},
       {names: 'Technology',sources:['techcrunch']},
       {names: 'Sports', sources:['espn','bleacher-report']},
       {names: 'Finance'},
       {names: 'Health'},
       {names: 'World'}
     ]
        }
    },

    created(){

    },
    methods(){

    }
}
</script>

<style >


</style>
