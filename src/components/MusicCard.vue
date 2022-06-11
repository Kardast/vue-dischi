<template>

  <div class="music-card">
    <img :src="musicObject.poster" :alt="musicObject.title">
    <div class="text-box">
      <h3>{{ musicObject.title }}</h3>
      <span>{{ musicObject.author }}</span> <br>
      <span>{{ musicObject.year }}</span>
    </div>
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
.music-card {
  width: calc(100% / 5 - 40px);
  height: 320px;
  padding-top: 20px;
  text-align: center;
  background-color: #2e3a46;
  margin: 10px 20px;
  box-sizing: border-box;

  img {
    width: 80%;
    height: 150px;
    object-fit: contain;
  }

  .text-box {
    padding: 5px 15px;
    h3 {
      color: white;
      font-size: 24px;
      margin-bottom: 10px;
    }
    span{
      color: grey;
    }
  }
}
</style>
