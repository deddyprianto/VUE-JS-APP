<template>
  <Block :delay="delay" v-if="isPlaying" @end="ending" />
  <button @click="start" :disabled="isPlaying">
    Play
  </button>
  <p v-if="isPlaying">Your score: {{ scored }}</p>
</template>
<script>
import Block from "./components/Block.vue";
export default {
  name: "App",
  components: { Block },
  data: function() {
    return {
      isPlaying: false,
      delay: null,
      scored: null,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random * 5000;
      this.isPlaying = true;
    },
    ending(reactionTimer) {
      this.scored = reactionTimer;
      this.isPlaying = false;
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
.text {
  color: #42b983;
  transition: 0.3s;
}
.change__text {
  color: red;
}
</style>
