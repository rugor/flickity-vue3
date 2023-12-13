<template>
  <div class="app">
    <flickity ref="flickity" :options="flickityOptions">
      <div class="carousel-cell">1</div>
      <div class="carousel-cell">2</div>
      <div class="carousel-cell">3</div>
      <div class="carousel-cell">4</div>
      <div class="carousel-cell">5</div>
      <div class="carousel-cell">6</div>
      <div class="carousel-cell">7</div>
      <div class="carousel-cell">8</div>
      <div class="carousel-cell">9</div>
      <div class="carousel-cell">10</div>
      <div class="carousel-cell">11</div>
      <div class="carousel-cell">12</div>
    </flickity>
  </div>
</template>

<script>
import { defineComponent } from 'vue'
import Flickity from './components/Flickity.vue'
export default defineComponent({
  name: 'App',
  components: {
    Flickity
  },
  data() {
    return {
      flickityOptions: {
        pageDots: false,
        wrapAround: true,
      }
    }
  }
})
</script>
<style>
body {
  margin: 0;
  padding: 0;
}
</style>
<style scoped>
.app {
  width: 900px;
  height: 100vh;
  margin: 0 auto; 
}
</style>