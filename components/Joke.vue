<template>
  <nuxt-link :to="'jokes/' + id" class="link">
    <div class="joke">
      <p>{{ joke }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'Joke',
  // eslint-disable-next-line vue/require-prop-types
  props: ['joke', 'id']
}
</script>

<style>
.joke {
  padding: 1rem;
  border: 1px dotted #ccc;
  margin: 1rem 0;
}

.link {
  text-decoration: none;
  color: #000;
}
</style>
