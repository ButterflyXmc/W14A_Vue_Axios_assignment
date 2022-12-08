<template>
  <div>
    <button @click="getLoudJokes">LOUD</button>
    <div class="loud" v-for="joke in loudJokes" :key="joke">
      <h3>{{ joke.toUpperCase() }}</h3>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "jokeButton",
  data() {
    return {
      loudJokes: "",
    };
  },
  methods: {
    getLoudJokes() {
      axios
        .get("https://geek-jokes.sameerkumar.website/api?format=json")
        .then((response) => {
          //   console.log(response.data);
          this.loudJokes = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
  // Not working for me :(
  // mounted() {
  //   this.$root.$on("getJokes", this.loudJokes);
  // },
};
</script>

<style scoped>
.loud {
  color: blue;
  /* text-transform: uppercase; */
}
</style>