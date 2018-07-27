<template>
  <div class="hello">

   <select v-on:change="selectedTopic">
     <option value="">Select a topic...</option>
     <option v-for="(topic,index) in topics" :key="index">{{topic.names}} </option>
   </select>

   <!-- <ul class="nav">
     <li class="nav-item" v-for="(topic,index) in topics" :key="index" v-on:click="selectedTopic(topic)">{{topic.names}}</li>
   </ul> -->
<ul>
  <li>

  </li>
</ul>
    

  
    <ul>
      <li class="card" v-for="(article,index) in articles" :key="index">
        <div class="col-1">
            <a class="url" :href="article.url">
              <img :src="article.urlToImage"/>
            </a>
       </div>
        <div class="col-2">
           <h2>{{article.title}}</h2>
           <p>{{ article.author }} </p>
           <p>{{ article.description}}</p>
           <button class="card-button" v-on:click="article.url">Read full article</button>
         </div>
      </li>
    </ul>
   

  
  </div>
</template>

<script>
import axios from 'axios'

export default {

  name: 'HelloWorld',
 data(){
   return{
     articles: '',
     topics:[
       {names: 'bloomberg'},
       {names: 'bbc-news'},
       {names: 'espn'},
       {names: 'techcrunch'},
       {names: 'bleacher-report'},
       {names: 'abc-news'}
     ],
    select:''
  
   }
 },
  methods:{
    getTopicName (id) {
      console.log(id.names);
  

 },
   selectedTopic(topic){
     this.select = event.target.value;

     
   axios.get("https://newsapi.org/v2/top-headlines?sources="+this.select+"&apiKey=46e3d27e0d0e4789b695d7134a1dd1cc")
    .then((response)=>(this.articles = response.data.articles)).catch((error)=>(console.log(error)))

     console.log(this.select);
   }
 
 },


 }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
select{
  margin: 15px auto;
  padding: 10px;
  width: 90%;
  border-radius: 10px;
  font-size: 1.1rem;
}
select option{
  border:none;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  border-radius: 10px;
}

.hello{
  width: 100%;
  background-color: rgba(15, 17, 22, 0.925);
  margin: 0;
}
ul{
  padding: 0;
}
.card{
  display: grid;
  grid-template-columns: 1fr 1fr;
  background-color:rgb(255, 255, 255);
  margin: 0 auto;
  padding: 20px;
  border-bottom: 1px solid grey;
  grid-template-rows: 350px;
  width: 60%;
}
.col-1{
  margin-right: 10px;
   border-radius: 20px;
}
img{
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  /* box-shadow: 4px 8px 8px 0 grey; */

}
a{
  
  margin: 0;
  padding: 0;
}
.col-2{
   
   background-color: white;
 
   padding: 10px;
}
.card-button{
  border:none;
  padding: 10px;
  width: 40%;
  border-radius: 20px;
  background-color: rgba(60, 60, 255, 0.753);
  color: white;
  font-size: 1rem;
}
.card:hover{
   transition:transform .5s;
  transform:scale(1.01);
   box-shadow: 1px 4px 4px 0 grey;
    border: 1px solid grey;

}
.nav{width: 90%; margin: 0; padding: 0;}

.nav-item{list-style-type: none;
 display: inline; 
 margin: 0 6px;
 font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
font-size: 1rem;
color: white;
border-bottom:1px solid black;
text-transform: uppercase;
padding: 8px;

 }
 .nav-item:hover{
background-color: white;
color: blue;
border-bottom:3px solid blue;
transition: .5s;

 }



.card-button:hover{
  cursor: pointer;
 background-color: rgba(60, 60, 255, 1);
 transition: .5s;
}
@media screen and (max-width: 800px){
  .card{
    display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: auto;
  margin: 0 auto;
  width: 80%;
}
.card-button{
  width: 100%;
}
.col-1,.col-2{
  margin: 0 auto;
}

}

</style>
