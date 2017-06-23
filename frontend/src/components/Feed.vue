<template>
  <div v-if="loading">
    {{ loadingText }}
  </div>
  <div v-else class="feed">
    <ul>
      <li v-for="tweet in tweets"><tweet :tweet="tweet"/></li>
    </ul>
  </div>
</template>

<script>
import Tweet from './Tweet'
export default {
  name: 'feed',
  components: {Tweet},
  props: ['tweets', 'loading'],
  data () {
    return {
      language: 'en'
    }
  },
  computed: {
    loadingText: function () {
      if (this.language === 'fr') {
        return 'Chargement des tweets en cours ...'
      } else {
        return 'Loading tweets ...'
      }
    }
  }
}
</script>

<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
 list-style-type: none;
 padding: 0;
}
li {
 display: block;
 margin: 0 10px;
}
</style>
