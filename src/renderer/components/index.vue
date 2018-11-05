<template>
  <div>
    <HeaderItem/>
    <App/>
    <FooterItem/>
  </div>
</template>

<script>
  import HeaderItem from './HeaderItem'
  import FooterItem from './FooterItem'
  import App from './App'

  const remote = require('electron').remote
  const app = remote.app
  const path = app.getAppPath()

  console.log(path)

  const exec = require('child_process').execFile

  export default {
    name: 'index',
    components: {
      HeaderItem, FooterItem, App
    },
    method: {
      exec: exec(path + '/', {}, function () {})
    }
  }
</script>