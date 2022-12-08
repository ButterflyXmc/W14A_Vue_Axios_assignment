<template>
  <div>
    <!--4.This button will trigger the function getJokes -->
    <button @click="getJokes">Jokes</button>
    <div v-for="joke in jokes" :key="joke">
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
      //2. API result will be printed in here
      jokes: "",
    };
  },
  methods: {
    //1.This function is calling the API
    getJokes() {
      axios
        .get("https://geek-jokes.sameerkumar.website/api?format=json")
        .then((response) => {
          //   console.log(response.data);
          //3. jokes is an empty string = the data from the API
          this.jokes = response.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style scoped>
</style>