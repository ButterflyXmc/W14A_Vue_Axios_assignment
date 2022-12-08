<template>
  <div>
    <button @click="getSnakeJokes">Snake</button>
    <div v-for="joke in snakeJokes" :key="joke">
      <!-- using replaceAll(replace space(empty string), with underscore(_))-->
      <h3>{{ joke.replaceAll("", "_") }}</h3>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "jokeButton",
  data() {
    return {
      snakeJokes: "",
    };
  },
  methods: {
    getSnakeJokes() {
      axios
        .get("https://geek-jokes.sameerkumar.website/api?format=json")
        .then((response) => {
          //   console.log(response.data);
          this.snakeJokes = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  // mounted() {
  //   this.$root.$on("getJokes", this.snakeJokes);
  // },
};
</script>

<style scoped>
h3 {
  color: green;
}
</style>