<template>
  <h1>Deddy Reaction Timmer</h1>
  <button @click="calback">Play</button>
</template>
<script>
export default {
  name: "App",
  components: {},
  data: function() {
    return {
      isPlaying: false,
      delay: null,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
    },
  },
};
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
