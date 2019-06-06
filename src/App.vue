<template>
  <div id="app">


    <header>
      <section class="jumbotron">
        <div class="container text-center">
   <h1 class="display-1">Your Daily News</h1>
        <p class="lead">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Reprehenderit corporis vel expedita, officiis quaerat dignissimos possimus qui esse, libero iusto iste perferendis, ratione eveniet praesentium similique cumque. Doloribus, repellat aperiam.</p>
      
        </div>
     </section>
    </header>


    <router-view/>
  
  
  
  </div>
</template>

<style>
#app {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  

}
#nav {
  text-align: center;
  padding: 30px;
 

}

#nav a {
  font-weight: bold;
  color: black;
  font-size: 1.3rem;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: rgb(33, 52, 223);
}
#nav ul li{
display: inline;
margin-left: 8px;
}
p{
  font-size: 1.4rem;
}
</style>
