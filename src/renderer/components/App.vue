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
  const path = require('path')
  const remote = require('electron').remote
  const app = remote.app
  const exeDirPath = path.dirname(app.getPath('exe'))
  console.log(exeDirPath)

  const exec = require('child_process').execFile

  export default{
    data: function () {
      return {
        gamejson: JSON.parse(fs.readFileSync(exeDirPath + '/' + this.jsonpath, 'utf8'))
      }
    },
    props: ['jsonpath'],
    methods: {
      exec () {
        exec('/', {}, function () {})
      }
    }
  }
</script>