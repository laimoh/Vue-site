<template>
  <div class="carousel">
    <slot></slot>
  </div>
  <div class="btns">
    <button @click="prev" class="prev">☜</button>
    <button @click="next" class="next">☞</button>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    next() {
      this.$emit("next");
    },
    prev() {
      this.$emit("prev");
    }
  }
};
</script>

<style scoped>
.carousel {
  margin: auto;
  display: flex;
  justify-content: center;
  width: 60vw;
  height: 60vh;
  overflow: hidden;
}

button {
  position: relative;
  outline: none;
  border: none;
  cursor: pointer;
  background: transparent;
  -webkit-appearance: none;
  -moz-appearance: none;
  /* top: 35vh; */
  font-size: 2rem;
  color: white;
}

button:active,
button:hover {
  outline: none;
  color: var(--orange-text-color);
}

.btns {
  position: relative;
  top: -30vh;
}

.next {
  left: 64vw;
}

.prev {
  /* left: -4vw; */
}
</style>