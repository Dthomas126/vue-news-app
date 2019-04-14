<template>
  <div id="app">
    <div id="nav">
      <ul>
        <li>      <router-link to="/">Home</router-link>
  </li>
        <li>      <router-link to="/about">About</router-link>
</li>
      </ul>
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
  color: #2c3e50;
}
#nav {
  text-align: center;
  padding: 30px;
  background-color:  rgb(33, 52, 223);

}

#nav a {
  font-weight: bold;
  color: white;
  font-size: 1.3rem;
  text-decoration: none;
}

#nav a.router-link-exact-active {
  color: rgb(30, 224, 24);
}
#nav ul li{
display: inline;
margin-left: 8px;
}
p{
  font-size: 1.4rem;
}
</style>
