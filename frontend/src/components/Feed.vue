<template>
  <div class="feed">
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
  props: ['tweets']
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
