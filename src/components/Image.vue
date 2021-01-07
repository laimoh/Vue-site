<template>
  <div class="visual" :class="{ IL:theme === 'IL', subtext:theme === 'subtext' }">
    <img :class="{ noshadow:theme === 'noshadow'}" :src="imgSrc" />
  </div>
</template>

<script>
export default {
  props: ["theme", "imgSrc"]
};
</script>

<style scoped>
.visual.IL {
  width: 33vw;
  margin: auto;
  /* outline: black 1px solid; */
}

.visual.subtext {
  width: 68vw;
  margin: auto;
}

.visual.subtext img {
  /* box-shadow: none; */
  border-radius: 25px;
}

.visual img.noshadow {
  box-shadow: none;
}

.visual img {
  width: 100%;
  height: auto;
  border-radius: 20px;
  box-shadow: 0px 7px 12px 10px rgba(0, 0, 0, 0.62);
}
</style>