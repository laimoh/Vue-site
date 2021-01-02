<template>
  <div class="grad" :class="{ WP:theme === 'WP' }">
    <div class="box" :class="{ WP:theme === 'WP' }">
      <div class="footer">
        <slot name="footer"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"]
};
</script>

<style>
.grad {
  height: 56%;
  width: 4vw;
  border-radius: 25px;
  box-shadow: inset 0 0 12px 15px rgba(114, 107, 107, 0.986),
    inset 0 0 3px 2px rgba(114, 107, 107, 0.986);
  background: var(--main-border-color);
  display: flex;
  justify-content: center;
  align-items: center;
}

.grad.WP {
  box-shadow: inset 0 0 10px 5px rgba(114, 107, 107, 0.986),
    inset 0 0 3px 2px rgba(114, 107, 107, 0.986);
  width: 67vw;
  height: 15vh;
  /* opacity: 0.5; */
}

.box {
  height: 55%;
  width: 2vw;
  border-radius: 25px;
  /* background: rgba(114, 107, 107, 0.79); */
  /* display: none; */
}

.box.WP {
  display: none;
}

.footer.WP {
  display: none;
}

.footer {
  font-family: "Space Mono", monospace;
  color: var(--orange-text);
  height: 40%;
  display: flex;
  flex-direction: column;
  white-space: nowrap;
  justify-content: space-around;
  align-items: center;
}

.footer h1 {
  font-size: 0.9rem;
  transform: rotate(90deg);
}
.footer p {
  /* font-size: 0.9rem; */
  /* transform: rotate(90deg); */
}
</style>