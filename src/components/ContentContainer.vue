<template>
  <div class="content-container">
    <div class="navbar">

      <img src="../assets/img/logo-small.svg" alt="logo">
    </div>

    <div class="cards-container">

    </div>

  </div>
</template>

<script>
export default {
  name: 'ContentContainer',
  // props: {

  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  .navbar{
    background-color: #2e3a46;
    height: 100px;
    display: flex;
    align-items: center;
    padding-left: 20px;

    img{
      height: 60px;
    }
  }

  .cards-container{
    background-color: #1e2d3b;
    height: calc(100vh - 100px);
  }
</style>
