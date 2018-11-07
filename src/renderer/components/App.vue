<template>
  <article class="box media">
    <figure class="media-left">
      <p class="image is-64x64">
      </p>
    </figure>
    <div class="media-content">
      <div class="content">
        <p><strong>{{ game.name }}</strong><br>
          {{ game.text }}
        </p>
        <button class="button is-info">
          Details
        </button>
        <button class="button is-primary" v-on:click="exec()">
          Play
        </button>
      </div>
    </div>
  </article>
</template>

<script>
  const remote = require('electron').remote
  const app = remote.app
  const path = app.getAppPath()
  const exec = require('child_process').execFile

  export default{
    data: function () {
      return {
        game: require('../assets/gamedata')
      }
    },
    methods: {
      exec () {
        console.log(path)
        exec(path + '/', {}, function () {})
      }
    }
  }
</script>