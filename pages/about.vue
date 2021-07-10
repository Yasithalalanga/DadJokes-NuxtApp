<template>
  <div>
    <app-header />
    <h1>About DAD jokes</h1>
    <p>This is an app that displays corny dad jokes.</p>
  </div>
</template>

<script>
import AppHeader from '../components/AppHeader.vue'

export default {
  components: {
    AppHeader
  },
  head () {
    return {
      title: 'About The App',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for corny dad jokes'
        }
      ]
    }
  }
}
</script>

<style></style>
