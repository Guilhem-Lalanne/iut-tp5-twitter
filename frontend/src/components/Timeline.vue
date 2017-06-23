<template>
  <div class="timeline">
    <h1>{{ msg }}</h1>
      <feed :tweets="tweets"/>
  </div>
</template>

<script>
import Feed from './Feed'
import Vue from 'vue'
import Resource from 'vue-resource'
Vue.use(Resource)
export default {
  name: 'timeline',
  data () {
    return {
      tweets: []
    }
  },
  methods: {
    fetchTweets: function () {
      this.$http.get('http://localhost:8080/list').then(response => {
        this.tweets = response.body
      },
      response => {
        // error callback
      })
    }
  },
  created () {
    this.fetchTweets()
  },
  components: {Feed}
}
</script>

<style scoped>

</style>
