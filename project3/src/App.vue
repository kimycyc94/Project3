<template>
  <div id="app">
    <Header />
    <div class="home-logo">
    <router-link to="/">
      <img src="/images/logo.png">
    </router-link>
  </div>
    <div id="content" class="content">
      <router-view></router-view>
    </div>
    <!--<router-view/>-->
  </div>
</template>


<script>
  import Header from './components/Header.vue';
  export default {
    name: "App",
    data()  {
      return {}
    },
    components: {
      Header
    },
    computed: {
      items() {
        return this.$root.$data.items;
      },
      sizeOfItems() {
        return this.items.length;
      }
    },
    methods: {
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

.home-logo img {
  width: 50%;
  border: 2px solid rgb(90, 88, 88);
}
#footer {
  margin-top: 60px;
  padding-top: 10px;
  padding-bottom: 10px;
  border: 3px solid white;
  text-align: center;
  border-top-color: rgb(92, 88, 84);
}

#footer a:hover {
  font-weight: bold;
}
</style>
