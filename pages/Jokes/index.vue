<template>
  <div>
    <app-header />
    <search-jokes @search-text="searchText" />
    <joke
      v-for="joke in jokes"
      :id="joke.id"
      :key="joke.id"
      :joke="joke.joke"
    />
  </div>
</template>

<script>
import Joke from '../../components/Joke.vue'
import AppHeader from '~/components/AppHeader.vue'
import SearchJokes from '~/components/SearchJokes.vue'

export default {
  components: {
    AppHeader,
    Joke,
    SearchJokes
  },
  data () {
    return {
      jokes: []
    }
  },
  head () {
    return {
      title: 'Dad Jokes',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for corny dad jokes'
        }
      ]
    }
  },
  async created () {
    const config = {
      headers: {
        Accept: 'application/json'
      }
    }
    try {
      const res = await this.$axios.get(
        'https://icanhazdadjoke.com/search',
        config
      )
      this.jokes = res.data.results
    } catch (err) {
      // eslint-disable-next-line no-console
      console.log(err)
    }
  },
  methods: {
    async searchText (text) {
      const config = {
        headers: {
          Accept: 'application/json'
        }
      }
      try {
        const res = await this.$axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        )
        this.jokes = res.data.results
      } catch (err) {
        // eslint-disable-next-line no-console
        console.log(err)
      }
    }
  }
}
</script>

<style></style>
