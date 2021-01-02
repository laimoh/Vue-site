<template>
  <div class="wrap" :class="{WP:theme === 'WP'}">
    <div class="b-heading">
      <h1>{{ heading }}</h1>
    </div>
    <div class="body-text">
      <p>{{ body }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme", "heading", "body"]
};
</script>

<style scoped>
.wrap {
  position: relative;
  top: 10vh;
  display: flex;
  width: 100%;
  height: 30vh;
  justify-content: space-evenly;
  align-items: center;
}
.b-heading h1 {
  font-family: "Roboto Mono", monospace;
  color: rgb(211, 211, 210);
  font-size: 11px;
  font-weight: normal;
  writing-mode: tb-rl;
  transform: rotate(-180deg);
  padding: 2rem 0.2rem;
  border: solid 0.5px rgb(211, 211, 210);
  border-radius: 25px;
  /* transition: all ease 0.5s; */
}

.body-text {
  width: 60vw;
}
.body-text p {
  font-family: "Space Mono", monospace;
  color: rgb(255, 255, 255);
  font-size: 13px;
}
</style>