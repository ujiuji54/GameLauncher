<template>
  <article class="box media">
    <figure class="media-left">
      <p class="image is-64x64">
      </p>
    </figure>
    <div class="media-content">
      <div class="content">
        <p><strong>{{ gamejson.name }}</strong><br>
          {{ gamejson.text }}<br>
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
  const fs = require('fs')
  const exec = require('child_process').execFile

  export default{
    data: function () {
      console.log(this.appDirPath)
      return {
        gamejson: JSON.parse(fs.readFileSync(this.appDirPath + '/' + this.jsonPath, 'utf8'))
      }
    },
    props: ['jsonPath', 'appDirPath'],
    methods: {
      exec () {
        exec('/', {}, function () {})
      }
    }
  }
</script>