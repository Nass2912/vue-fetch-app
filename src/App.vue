<template>
  <nav>
    <router-link to="/">Home</router-link>
    <router-link :to="{ name: 'about' }">About</router-link>
  </nav>
  <router-view />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  display: flex;
  justify-content: space-around;
  padding: 30px 0;
  background-color: rgba(85, 175, 130, 0.355);
}

nav a {
  font-weight: bold;
  text-decoration: none;
  font-size: 20px;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
