<template>
  <div class="search-bar">

    <input type="text" placeholder="Search"
    
    v-model="inputText"
    @keyup.enter="myFirstEmit()"
    >
        
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
        console.log(this.inputText);
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
