<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <ul>
      <li v-for="tweet in tweets">
        {{ tweet.auteur }} : {{ tweet.contenu }}
      </li>
    </ul>
  </div>
</template>

<script>
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
  }
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
