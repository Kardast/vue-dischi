<template>
  <div class="music-card">
    <img :src="musicObject.poster" :alt="musicObject.title">
  </div>
</template>

<script>
export default {
  name: 'MusicCard',
  props: {
    musicObject: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
