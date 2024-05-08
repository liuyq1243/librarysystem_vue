<template>
  <div>
    <div class="home">
      <div id="header-div">
        <carousel></carousel>

        <Reviews></Reviews>
      </div>
    </div>
  </div>
</template>

<script>
import Carousel from './Carousel.vue'
import Reviews from './Reviews.vue'

export default {
  name: 'AppIndex',
  components: {Reviews, Carousel}
}
</script>

<style scoped>
.home {
  width: 990px;
  margin-left: auto;
  margin-right: auto;
  margin-top: -20px;
}

#header-div {
  padding-bottom: 20px;
  padding-left: 5px;
  background-color: white;
  /*background: url("../../assets/img/bg/bg3.jpg");*/
}
</style>
