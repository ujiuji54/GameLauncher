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

  export default {
    name: 'index',
    components: {
      HeaderItem, FooterItem, App
    }
  }
</script>