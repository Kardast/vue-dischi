<template>
  <div class="content-container">

    <div id="loader" v-if="loading">LOADING ...</div>

    <div class="cards-container" v-else>

      <MusicCard v-for="(item, index) in musicList" :key="index" :musicObject="item" />
    </div>

  </div>
</template>

<script>
import axios from "axios";
import MusicCard from './MusicCard.vue';

export default {
  name: "ContentContainer",
  components: {
    MusicCard
  },
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      musicList: [],
      loading: true
    }
  },
  created() {
    this.getMusicList();
  },
  methods: {
    getMusicList() {
      axios
        .get(this.apiUrl)
        .then((result) => {
          this.musicList = result.data.response;
          console.log(this.musicList);
          this.loading = false;
        })
        .catch((error) => {
          console.log("Errore", error);
        })
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.content-container {
  background-color: #1e2d3b;
  height: calc(100vh - 100px);
  display: flex;
  justify-content: center;

  #loader{
    color: white;
    font-size: 50px;
    background-color: #2e475e;
    height: 70px;
    padding: 10px;
    margin-top: 15px
  }

  .cards-container {
    width: 70%;
    display: flex;
    flex-wrap: wrap;
    max-width: 1200px;
    padding-top: 30px;
  }
}
</style>
