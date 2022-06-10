<template>
  <div class="content-container">
    <div class="navbar">

      <img src="../assets/img/logo-small.svg" alt="logo">
    </div>

    <div class="cards-container">

      <div class="wrapper">

        <MusicCard v-for="(item, index) in musicList" :key="index" :musicObject="item" />
      </div>
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
      musicList: []
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
.navbar {
  background-color: #2e3a46;
  height: 100px;
  display: flex;
  align-items: center;
  padding-left: 20px;

  img {
    height: 60px;
  }
}

.cards-container {
  background-color: #1e2d3b;
  height: calc(100vh - 100px);
  display: flex;
  justify-content: center;

  .wrapper {
    width: 60%;
    display: flex;
    flex-wrap: wrap;
    min-width: 800px;
    max-width: 1200px;
    padding-top: 30px;
  }
}
</style>
