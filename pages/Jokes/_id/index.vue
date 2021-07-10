<template>
  <div>
    <app-header />
    <nuxt-link to="/jokes">
      Back To Jokes
    </nuxt-link>
    <h2>{{ joke }}</h2>
    <small>Joke ID: {{ $route.params.id }}</small>
  </div>
</template>

<script>
import AppHeader from '~/components/AppHeader.vue'
export default {
  components: { AppHeader },
  data () {
    return {
      joke: {}
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
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      )
      this.joke = res.data.joke
    } catch (err) {
      // eslint-disable-next-line no-console
      console.log(err)
    }
  }
}
</script>

<style></style>
