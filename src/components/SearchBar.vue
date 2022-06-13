<template>
  <div class="search-bar">

    <input type="text" placeholder="Search"
    
    v-model="inputText"
    @keyup.enter="myFirstEmit()"
    >
    <button @click.prevent="myFirstEmit()">Search</button>
    <button @click.prevent="resetSearch()">Clear</button>
    <select v-model="inputText" @click.prevent="myFirstEmit()" name="selection" id="select">
      <option value="">All</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="metal">Metal</option>
      <option value="jazz">Jazz</option>
    </select>
        
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
  data (){
    return {
        inputText: "",
    }
  },

  methods: {
    myFirstEmit(){
      this.$emit('mySearch', this.inputText);
    },
    resetSearch(){
      this.inputText= "";
      this.myFirstEmit();
    }
    
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.search-bar{
display: flex;
justify-content: center;
padding-top: 10px;
}
</style>
