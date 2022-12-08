<template>
  <div id="app">
    <JokesButton />
    <LoudJokes />
    <SnakeJokes />
    <NormalJokes />
  </div>
</template>

<script>
import NormalJokes from "@/components/NormalJokes.vue";
import LoudJokes from "@/components/LoudJokes.vue";
import JokesButton from "@/components/JokesButton.vue";
import SnakeJokes from "@/components/SnakeJokes.vue";

export default {
  name: "App",
  components: {
    JokesButton,
    NormalJokes,
    LoudJokes,
    SnakeJokes,
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
