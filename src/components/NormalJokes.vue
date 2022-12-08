<template>
  <div>
    <button @click="getNormalJokes">Normal</button>
    <div v-for="joke in normalJokes" :key="joke">
      <h3>{{ joke }}</h3>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "jokeButton",
  data() {
    return {
      normalJokes: [],
    };
  },
  methods: {
    getNormalJokes() {
      axios
        .get("https://geek-jokes.sameerkumar.website/api?format=json")
        .then((response) => {
          //   console.log(response.data);
          this.normalJokes = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  // Not working for me :(
  // mounted() {
  //   this.$root.$on("getJokes", this.normalJokes);
  // },
};
</script>

<style scoped>
h3 {
  color: red;
}
</style>