<template>
  <div class="tweet">
    <div>
      <strong>{{ tweet.auteur.prenom }}</strong>
      <strong>{{ tweet.auteur.nom }}</strong>
      <span class="handle">@{{ tweet.auteur.handle }} -- {{moment(tweet.date).fromNow()}}
</span>
    </div>
    <div>
      {{ tweet.contenu }}
    </div>
    <div>
      <ul>
        <li class="button">
          <icon name="reply"/>
        </li>
        <li class="button">
          <a @click="retweet()">
            <icon name="retweet"/>
            {{ tweet.retweeters.length }}
          </a>
        </li>
        <li class="button">
          <icon name="heart"/>
        </li>
        <li class="button">
          <icon name="envelope"/>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
  import 'vue-awesome/icons'
  import Icon from 'vue-awesome/components/Icon'
  import moment from 'moment'
  export default {
    created () {
      moment.locale('fr')
    },
    name: 'tweet',
    props: ['tweet'],
    components: { Icon },
    methods: {
      moment: function (date) {
        return moment(date)
      },
      retweet: function () {
        this.$http.get(
          'http://localhost:8080/retweet',
          {
            responseType: 'text',
            params: {
              utilisateur: 'snoopdog',
              tweet: this.tweet.id
            }
          }).then(response => {
          },
          response => {
          // error callback
          })
      }
    }
  }
</script>

<style scoped>
  li.button {
   display: inline-block;
  }

  a {
   color: #42b983;
  }

  span.handle {
   color: gray;
  }
</style>
