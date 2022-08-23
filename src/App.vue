<template>
  <h1>REACTION TIMER</h1>
  <button @click="start" :disabled="isStarted">start</button>
  <divButton v-if="isStarted" :delay="delay" />
</template>

<script>
import divButton from "./components/second-div.vue";

export default {
  name: "App",
  data() {
    return {
      isStarted: false,
      delay: null,
    };
  },
  components: {
    divButton,
  },
  methods: {
    start: function () {
      this.delay = 4000;
      this.isStarted = true;
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
  margin-top: 60px;
}
</style>
