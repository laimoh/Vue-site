<template>
  <transition name="left">
    <div v-show="visibleSlide === index" class="carousel-slide">
      <slot></slot>
    </div>
  </transition>
</template>

<script>
export default {
  props: ["visibleSlide", "index"],
  data() {
    return {};
  }
};
</script>

<style>
.carousel-slide {
}
.carousel-slide img {
  width: 100%;
  height: 100%;
}

.left-enter-active {
  animation: leftSlideIn 0.8s ease-in-out;
}

.left-leave-active {
  animation: leftSlideOut 0.8s ease-in-out;
}

@keyframes leftSlideIn {
  from {
    /* transform: translateX(-100%); */
    opacity: 0;
  }
  to {
    /* transform: translateX(0); */
    opacity: 1;
  }
}

@keyframes leftSlideOut {
  from {
    /* transform: translateX(-100%); */
    opacity: 1;
  }
  to {
    /* transform: translateX(100%); */
    opacity: 0;
  }
}
</style>