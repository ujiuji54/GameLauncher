<template>
  <div>
    <HeaderItem/>
    <router-link to='/'>Hello</router-link>
  </div>
</template>

<script>
  import HeaderItem from './HeaderItem'

  const remote = require('electron').remote
  const app = remote.app
  const path = app.getAppPath()

  console.log(path)

  const exec = require('child_process').execFile

  export default {
    name: 'index',
    components: {
      HeaderItem
    },
    method: {
      exec: exec(path + '/', {}, function () {})
    }
  }
</script>