<template>
  <div id="app">
    <div id="nav">
      <router-link :to="route('web-test')">Home</router-link> |
      <router-link :to="route('web-about')">About</router-link>
    </div>
    <router-view/>
  </div>
</template>  

<script>
import router from './router'
export default {
  router,
  props: ['root'],
  mounted() {
    console.log('web component test mounted: ', this.root)
  },
  methods: {
    route(path) {
      return `/${this.root}/${path}`
    }
  }
}
</script>

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
