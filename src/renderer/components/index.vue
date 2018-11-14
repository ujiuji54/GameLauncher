<template>
  <div>
    <App/>
    <HeaderItem/>
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
  console.log(exeDirPath)

  var fileList = []
  fs.readdir(exeDirPath, function (err, files) {
    if (err) throw err
    fileList = files.filter(function (file) {
      return fs.statSync(file).isFile() && /.*\.json$/.test(file)
    })
  })
  console.log(fileList)

  export default {
    name: 'index',
    components: {
      HeaderItem, FooterItem, App
    }
  }
</script>