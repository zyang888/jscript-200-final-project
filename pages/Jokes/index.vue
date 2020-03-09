<template lang="html">
<div>
  <SearchJokes v-on:search-text="searchText"/>
  <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
</div>
</template>

<script>
import axios from 'axios';
import Joke from '@/components/Joke'
import SearchJokes from '@/components/SearchJokes'

export default {
  head() {
    return {
      title: 'Dad Jokes',
      meta: [
        {
          hid: "hid_description",
          name: "name_description",
          content: "Best place for corny dad jokes"
        }
      ]
    }
  },
  data() {
    return {
      jokes: []
    }
  },
  components: {
    Joke,
    SearchJokes
  },
  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    }
    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config);
      this.jokes = res.data.results;
    } catch (err) {
      console.log(err);
    }
  },
  methods: {
    async searchText(text) {
      const config = {
        headers: {
          Accept: "application/json"
        }
      };
      try {
        const res = await axios.get(`https://icanhazdadjoke.com/search?term=${text}`, config);
        console.log(res);
        this.jokes = res.data.results;
      } catch (err) {
        console.log(err);
      }

    }
  }
};
</script>

<style lang="css" scoped>

</style>
