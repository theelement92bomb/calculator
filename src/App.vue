<template>
  <div id="nav">
    <router-link class="event-link" to="/">Calculator</router-link> |
    <router-link class="event-link" to="/Map">Map</router-link> |
    <router-link class="event-link" to="/Surprise">Surprise</router-link>
  </div>
  <div class="container">
    <router-view />
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
