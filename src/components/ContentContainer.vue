<template>
  <div class="content-container">

    <SearchBar @mySearch="searchMusic" />

    <div class="loader" v-if="loading">LOADING ...</div>

    <div class="cards-container" v-else>

      <MusicCard 
        v-for="(item, index) in filteredMusicCards" 
        :key="index" 
        :musicObject="item" 
      />
    </div>

  </div>
</template>

<script>
import axios from "axios";
import MusicCard from './MusicCard.vue';
import SearchBar from "./SearchBar.vue";

export default {
  name: "ContentContainer",
  components: {
    MusicCard,
    SearchBar
  },
  data() {
    return {
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      musicList: [],
      loading: true,
      userText: ""
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
    },
    searchMusic(textUser){
      this.userText = textUser;
    }
  },
  computed: {
    filteredMusicCards(){
      if (this.userText === "") {
        
        return this.musicList;
      } else {

        return this.musicList.filter(item => {
          return item.genre.toLowerCase().includes(this.userText.toLowerCase());
        });
      }
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.content-container {
  background-color: #1e2d3b;
  height: calc(100vh - 100px);
  width: 100%;

  .loader {
    color: white;
    font-size: 40px;
    background-color: #2e475e;
    height: 70px;
    padding: 10px;
    width: 300px;
    display: flex;
    margin: 15px auto;
    justify-content: center;
  }

  .cards-container {
    width: 70%;
    display: flex;
    flex-wrap: wrap;
    max-width: 1200px;
    padding-top: 30px;
    margin: 0 auto;
  }
}
</style>
