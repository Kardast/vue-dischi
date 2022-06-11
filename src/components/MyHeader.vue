<template>

    <div class="navbar">

        <img src="../assets/img/logo-small.svg" alt="logo">
    </div>
</template>

<script>
export default {
    name: 'MyHeader'
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
</style>