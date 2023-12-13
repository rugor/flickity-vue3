<template>
  <div ref="root" class="flickity">
    <slot />
  </div>
</template>
<script>
import { defineComponent, onMounted, onUnmounted, ref } from 'vue'
import Flickity from 'flickity'

export default defineComponent({
  props: {
    options: Object,
  },
  setup(props) {
    let flickity = null;
    const root = ref(null);
    onMounted(() => flickity = new Flickity(root.value, props.options));
    onUnmounted(() => flickity && flickity.destroy());
    return {
      root
    };
  },
})
</script>
<style>

.flickity .carousel {
  background: #EEE;
  margin-bottom: 40px;
}
/* use ::v-deep to get at slot elements */
.flickity .carousel-cell {
  height: 300px;
  width: 33.333%;
  margin: 0 10px;
  background: #6C6;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
}
/*! Flickity v3.0.0
https://flickity.metafizzy.co
---------------------------------------------- */
.flickity-enabled{position:relative}.flickity-enabled:focus{outline:0}.flickity-viewport{overflow:hidden;position:relative;height:100%;touch-action:pan-y}.flickity-slider{position:absolute;width:100%;height:100%;left:0}.flickity-rtl .flickity-slider{left:unset;right:0}.flickity-enabled.is-draggable{-webkit-tap-highlight-color:transparent;user-select:none}.flickity-enabled.is-draggable .flickity-viewport{cursor:move;cursor:grab}.flickity-enabled.is-draggable .flickity-viewport.is-pointer-down{cursor:grabbing}.flickity-cell{position:absolute;left:0}.flickity-rtl .flickity-cell{left:unset;right:0}.flickity-button{position:absolute;background:hsl(0 0% 100% / 75%);border:none;color:#333}.flickity-button:hover{background:#fff;cursor:pointer}.flickity-button:focus{outline:0;box-shadow:0 0 0 5px #19f}.flickity-button:active{opacity:.6}.flickity-button:disabled{opacity:.3;cursor:auto;pointer-events:none}.flickity-button-icon{fill:currentColor}.flickity-prev-next-button{top:50%;width:44px;height:44px;border-radius:50%;transform:translateY(-50%)}.flickity-prev-next-button.previous{left:10px}.flickity-prev-next-button.next{right:10px}.flickity-rtl .flickity-prev-next-button.previous{left:auto;right:10px}.flickity-rtl .flickity-prev-next-button.next{right:auto;left:10px}.flickity-prev-next-button .flickity-button-icon{position:absolute;left:20%;top:20%;width:60%;height:60%}.flickity-page-dots{position:absolute;width:100%;bottom:-25px;text-align:center;display:flex;justify-content:center;flex-wrap:wrap}.flickity-rtl .flickity-page-dots{direction:rtl}.flickity-page-dot{display:block;width:10px;height:10px;padding:0;margin:0 8px;background:hsl(0 0% 20% / 25%);border-radius:50%;cursor:pointer;appearance:none;border:none;text-indent:-9999px;overflow:hidden}.flickity-rtl .flickity-page-dot{text-indent:9999px}.flickity-page-dot:focus{outline:0;box-shadow:0 0 0 5px #19f}.flickity-page-dot.is-selected{background:hsl(0 0% 20% / 100%)}
</style>