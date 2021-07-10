<template>
  <div>
    <app-header />
    <h3 class="top_desc">
      Welcome to corny Dad Jokes in Web App.
    </h3>
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
      title: 'Welcome to Dad Jokes',
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

<style scoped>
.top_desc {
  display: flex;
  justify-content: center;
}
</style>
