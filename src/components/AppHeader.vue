<template>
  <header>
    <nav>
      <img src="https://www.freepnglogos.com/uploads/spotify-logo-png/spotify-download-logo-30.png" alt="">
    </nav>

  </header>
</template>

<script>
export default {
  name: 'AppHeader',
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import '../style/variables';
header {
  height: 50px;
  background-color: $bgCard;
  nav {
    position: relative;
    height:100%;
    img {
    width: 40px;
    position: absolute;
    left: 30px;
    top: 5px;
    }
  }
}

</style>
