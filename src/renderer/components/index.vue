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

  const fs = require('fs')
  const path = require('path')
  const remote = require('electron').remote
  const app = remote.app
  const exeDirPath = path.dirname(app.getPath('exe'))

  let fileList = fs.readdirSync(exeDirPath).filter(function (file) {
    if (file.endsWith('.json')) return file
  })
  console.log(fileList)

  export default {
    name: 'index',
    components: {
      HeaderItem, FooterItem, App
    }
  }
</script>