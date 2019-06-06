<template>
  <div class="container p-5">

<div class="row">
 
    <section  v-for="(article,index) in articles" :key="index" class=" col-sm-12 mb-4 ">
      
     <section class="card" style="border:none;">
       <div class="row">
         <div class="col">
          <div class="card-body">
                  <h2 class="card-title">{{article.title}}</h2>
                  <p class="" v-if="article.author">Author: {{ article.author }} </p>
                  <p class="card-text">Source: {{ article.description}}</p>
                  <a v-on:click="article.url">Read full article</a>
                </div>
         </div>
         <div class="col">
          
              <img class=" img-fluid" :src="article.urlToImage"/>
    
         </div>
       </div>
      <hr>
      
      

      </section>
  </section>
</div>
  
    
   

  
  </div>
</template>

<script>
import axios from 'axios'

const API_KEY = '46e3d27e0d0e4789b695d7134a1dd1cc';

export default {

  name: 'HelloWorld',
 data(){
   return{

     articles: '',
  
    select:'cnn'
   
   }
 },
 created(){
    axios.get("https://newsapi.org/v2/top-headlines?sources="+this.select+"&apiKey="+API_KEY)
    .then((response)=>(this.articles = response.data.articles)).catch((error)=>(console.log(error)))
 },
  methods:{
    getTopicName (id) {
    console.log(id.names);
 },
   selectedTopic(){
     this.select = event.target.value;
     console.log(this.select);
   }
 
 },


 }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>



</style>
