<template>
  <div>
    <HeaderItem/>
    <App
      v-for = "file in fileList"
      v-bind:jsonpath = "file"
    ></App>
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
  console.log('アプリがあるdirectoryのpath: ' + exeDirPath)

  let fileList = fs.readdirSync(exeDirPath).filter(function (file) {
    if (file.endsWith('.json')) return file
  })
  console.log(fileList)

  export default {
    name: 'index',
    data: function () {
      return {
        fileList: fileList
      }
    },
    components: {
      HeaderItem, FooterItem, App
    }
  }
</script>