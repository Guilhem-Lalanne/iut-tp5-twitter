<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <ul>
      <li v-for="tweet in tweets">
        <tweet :tweet="tweet"/>
      </li>
    </ul>
  </div>
</template>

<script>
import Tweet from './Tweet'
export default {
  name: 'hello',
  data () {
    return {
      tweets: [
        {auteur: 'user01', contenu: 'tweet 1'},
        {auteur: 'user02', contenu: 'tweet 2'},
        {auteur: 'user03', contenu: 'tweet 3'}
      ]
    }
  },
  components: {Tweet}
}
</script>

<style scoped>
  ul {
    list-style-type: none;
    padding: 0;
  }
  li {
    display: block;
    margin: 0 10px;
  }
</style>
