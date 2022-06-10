<template>
    
  <div class="music-card">
    <img :src="musicObject.poster" :alt="musicObject.title">
    <div>
        <!-- <h3>{{musicObject.title}}</h3> -->
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
.music-card{
    width: calc(100% / 5 - 40px);
    display: flex;
    justify-content: center;
    align-items: top;
    padding-top: 20px;
    background-color: #2e3a46;
    margin: 10px 20px;

    img{
        width: 150px;
        height: 150px;

    }
}
</style>
