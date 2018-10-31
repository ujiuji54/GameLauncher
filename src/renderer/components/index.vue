<template>
  <div>
    <router-link to='/'>Hello</router-link>
    <header></header>
  </div>
</template>

<script>
  import Header from './components/header'

  const remote = require('electron').remote
  const app = remote.app
  const path = app.getAppPath()

  console.log(path)

  const exec = require('child_process').execFile

  export default {
    name: 'index',
    components: {
      Header
    },
    method: {
      exec: exec(path + '/', {}, function () {})
    }
  }
</script>