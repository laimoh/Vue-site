<template>
  <div
    class="wrap"
    :class="{ WP:theme === 'WP', REC:theme === 'REC', IL:theme === 'IL', subtext:theme === 'subtext', reverse:theme === 'reverse' }"
  >
    <div class="b-heading" :class="{ reverse:theme === 'reverse' }">
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
  display: flex;
  width: 100%;
  height: 30vh;
  justify-content: space-evenly;
  align-items: center;
}

.wrap.WP {
  top: 10vh;
}

.wrap.IL {
  top: 15vh;
  height: 24vh;
  /* margin-bottom: 5vh; */
}

.wrap.subtext {
  flex-direction: row;
  /* margin-bottom: 5vh; */
}

.wrap.reverse {
  flex-direction: row-reverse;
  /* margin-bottom: 5vh; */
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

.b-heading.reverse {
  transform: rotate(180deg);
}

.body-text {
  width: 60vw;
}

.subtext .body-text {
  padding: 0vw 1vw;
  width: 25vw;
}

.reverse .body-text {
  padding: 0vw 1vw;
  width: 25vw;
}

.body-text p {
  font-family: "Space Mono", monospace;
  color: rgb(255, 255, 255);
  font-size: 13px;
}
</style>