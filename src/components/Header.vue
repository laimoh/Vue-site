<template>
  <div class="header" :class="{ WP:theme === 'WP' }">
    <div class="title">
      <p>{{ header }}</p>
    </div>
    <div class="worktype">
      <p>✧ {{types[0]}}</p>
      <p>✧ {{types[1]}}</p>
    </div>
    <div class="time">
      <p>{{types[2]}}</p>
    </div>
  </div>
</template>


<script>
export default {
  props: ["header", "types", "theme", "scrolled"]
  //   watch: {
  //      "scrolled"
  //   }
};
</script>

<style scoped>
.header {
  position: fixed;
  width: 65%;
  height: 10vh;
  display: flex;
  justify-content: space-around;
  align-items: flex-end;
  padding-bottom: 10px;
  font-style: oblique;
  color: rgb(255, 255, 255);
  /* mix-blend-mode: difference; */
  z-index: 10;
}

.blend {
  mix-blend-mode: difference;
}

.header.subtext {
  position: relative;
}
.title {
  width: 35%;
  font-family: "Space Mono", monospace;
  font-style: oblique;
  font-size: 1.8rem;
  align-self: flex-end;
  font-weight: bold;
}

.worktype {
  font-size: 0.8rem;
}

.time {
  font-style: oblique;
  font-size: 0.8rem;
}
</style>