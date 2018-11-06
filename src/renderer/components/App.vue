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
        <a class="button is-info">
          Details
        </a>
      </div>
    </div>
  </article>
</template>

<script>
  export default{
    data: function () {
      return {
        game: require('../assets/gamedata')
      }
    }
  }
</script>