<template>
  <div id="app">
    <MyHeader/>
    <ContentContainer/>
  </div>
</template>

<script>
import ContentContainer from './components/ContentContainer.vue';
import MyHeader from './components/MyHeader.vue';


export default {
  name: 'App',
  components: {
    ContentContainer,
    MyHeader
}
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
