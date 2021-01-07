<template>
  <div class="vid" :class="{ IL:theme === 'IL' }">
    <video autoplay controls :src="vidSrc"></video>
  </div>
</template>

<script>
export default {
  props: ["theme", "vidSrc"]
};
</script>

<style scoped>
.vid {
  position: relative;
  top: 20vh;
  width: 92%;
  height: 74%;
  border-radius: 25px;
  margin: auto;
  box-shadow: 0px 7px 12px 10px rgba(0, 0, 0, 0.62);
}

.vid.IL {
  margin-bottom: 30vh;
}
video {
  width: 100%;
  height: auto;
  border-radius: 25px;
}
</style>