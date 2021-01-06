<template>
  <div class="introVid top">
    <video controls :src="vidSrc"></video>
  </div>
</template>

<script>
export default {
  props: ["theme", "vidSrc"]
};
</script>

<style scoped>
</style>