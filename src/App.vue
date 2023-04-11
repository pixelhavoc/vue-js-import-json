<template>
  <nav>
    <router-link v-bind:to="{ name: 'home' }">Home</router-link> |
    <router-link v-bind:to="{ name: 'about' }">About</router-link> |
    <router-link v-bind:to="{ name: 'jobs' }">Jobs</router-link>
  </nav>

  <button v-on:click="redirect">Redirect</button>
  <button v-on:click="back">Go back</button>
  <button v-on:click="forward">Go forward</button>

  <router-view/>
</template>

<script>
export default {
  methods: {
    redirect() {
      this.$router.push({ name: 'home' })
    },
    back() {
      this.$router.go(-1)
    },
    forward() {
      this.$router.go(+1)
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

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 10px;
  border-radius: 4px;
}

nav a.router-link-exact-active {
  color: white;
  background: crimson;
}

button {
  margin: 0 10px;
  padding: 10px;
  border: none;
  border-radius: 4px;
}
</style>
