<template>
  <div class="giant-container">
    <div style="width: 20vw; margin-left: 0.5rem;" class="gradient">
      <div class="container index">
        <div class="contact">
          <h1>IG</h1>
          <h1>MAIL</h1>
          <h1>BLOG</h1>
        </div>
        <div class="list">
          <div class="wrapper">
            <h1 @click="closeProjects">{{ title }}</h1>
          </div>
          <ul>
            <li @click="openWindPoetry">☞ Wind Poetry</li>
            <li @click="openRec">
              ☞ Would You Like
              <br />A Receipt?
            </li>
            <li>☞ Typed Speech</li>
            <li>☞ Shek Leung</li>
            <li>☞ Invisible Lines</li>
            <li>☞ Yazdani Bakery</li>
          </ul>
        </div>
      </div>
    </div>
    <div class="gradient">
      <div style="width: 97%;" class="project container">
        <transition name="fade">
          <div v-if="showWP" class="backdrop" @scroll.passive="handleScroll">
            <Header
              theme="WP"
              header="Wind Poetry"
              :types="['Interaction','Data Visualisation','2020']"
            ></Header>
            <BodyText
              theme="WP"
              heading="ABOUT"
              body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Vivamus lobortis sapien porttitor, molestie urna ut, varius neque. In eu dapibus lectus. Etiam consequat, massa ut consequat lacinia, velit dui molestie dolor, id dapibus sem justo a ante. In pellentesque, odio ut pharetra congue, quam tellus efficitur arcu, non mattis risus nibh ac turpis."
            ></BodyText>
            <div class="introImg">
              <video
                alt="GIF DEMO"
                loop
                autoplay="autoplay"
                src="./assets/wind/wind_poetry-demo-1.mp4"
              ></video>
            </div>
            <BodyText
              theme="WP"
              heading="PROCESS"
              body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Vivamus lobortis sapien porttitor, molestie urna ut, varius neque. In eu dapibus lectus. Etiam consequat, massa ut consequat lacinia, velit dui molestie dolor, id dapibus sem justo a ante. In pellentesque, odio ut pharetra congue, quam tellus efficitur arcu, non mattis risus nibh ac turpis."
            ></BodyText>
            <div class="introVid">
              <video controls src="./assets/wind/wind_poetry-demo.mp4"></video>
            </div>
            <BodyText theme="WP" heading="TOOLS" body="✧ p5.js"></BodyText>
          </div>
        </transition>
        <transition name="fade">
          <div v-if="showRec" class="backdrop">
            <Header
              theme="REC"
              header="Would you like a receipt?"
              :types="['Chrome Extension','Data Visualisation','2020']"
            ></Header>
          </div>
        </transition>
      </div>
    </div>
    <Gradient>
      <template v-slot:footer>
        <h1>Laiqa Mohid</h1>
        <h1>©2020</h1>
      </template>
    </Gradient>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Gradient from "./components/Gradient.vue";
import BodyText from "./components/BodyText.vue";

export default {
  name: "App",
  components: {
    Header,
    Gradient,
    BodyText
  },
  data() {
    return {
      title: "LIST OF WORKS",
      ProjTitle: "Wind Poetry",
      showWP: false,
      showRec: false
    };
  },
  methods: {
    openWindPoetry() {
      (this.title = "BACK TO HOME"),
        (this.showWP = true),
        (this.showRec = false);
    },
    openRec() {
      (this.title = "BACK TO HOME"),
        (this.showRec = true),
        (this.showWP = false);
    },
    closeProjects() {
      this.title = "LIST OF WORKS";
      this.showWP = false;
      this.showRec = false;
    },
    handleScroll(e) {
      var scrollPos = e.target.scrollTop;
      let h = document.querySelector(".header");
      if (scrollPos > 1) {
        h.classList.add("blend");
      } else {
        h.classList.remove("blend");
      }
      // console.log(scrollPos);
    }
  }
};
</script>

<style>
#app {
  font-family: "Roboto Mono";
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.blend {
  mix-blend-mode: difference;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease-out !important;
}

.fade-enter,
.fade-leave-to {
  opacity: 0 !important;
}

.giant-container {
  display: flex;
  width: 100vw;
  height: 100vh;
  overflow: hidden;
  background: rgba(114, 107, 107, 0.986);
  justify-content: flex-start;
  align-items: center;
}

.gradient {
  height: 95%;
  width: 75%;
  border-radius: 25px;
  box-shadow: inset 0 0 12px 15px rgba(114, 107, 107, 0.986),
    inset 0 0 3px 2px rgba(114, 107, 107, 0.986);
  background: var(--main-border-color);
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  height: 95%;
  border-radius: 25px;

  background: rgba(114, 107, 107, 0.986);
}

.index {
  width: 90%;
  display: flex;
  flex-direction: column-reverse;
  align-items: center;
  justify-content: flex-start;
  background: rgba(114, 107, 107, 0.89);
}

.project {
  width: 90%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: rgba(114, 107, 107, 0.705);
}

.contact {
  height: 5%;
  width: 90%;
  font-size: 0.4rem;
  margin-bottom: 2rem;
  display: flex;
  justify-content: space-around;
  font-family: "Roboto Mono", monospace;
}

.contact h1 {
  border: solid 1px rgb(189, 135, 65);
  border-radius: 18%;
  color: var(--project-text-color);
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 18px;
  font-weight: normal;
  padding: 0px 10px;
  cursor: pointer;
}

.contact h1:hover {
  color: rgb(189, 135, 65);
  border: solid 1px var(--project-text-color);
}

.list {
  height: 85%;
  list-style: none;
  display: flex;
  border-radius: 25px;
}

.wrapper h1 {
  font-family: "Roboto Mono", monospace;
  color: var(--project-text-color);

  font-size: 12px;
  font-weight: normal;
  writing-mode: tb-rl;
  transform: rotate(-180deg);
  padding: 0.8rem 0.2rem;
  border: solid 0.5px rgb(189, 135, 65);
  margin-left: 2rem;
  border-radius: 25px;
  transition: all ease 0.5s;
}

.wrapper h1:hover {
  cursor: pointer;
  color: var(--project-text-color);
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  font-family: "Space Mono", monospace;
  color: var(--project-text-color);
  font-size: 15px;
  margin-top: 8rem;
  margin-right: 2.5rem;
  white-space: nowrap;
}

.indent {
  margin-left: 1rem;
}

.list li {
  margin: 2rem 0rem;
  /* color: var(--main-bg-color); */
  transition: all 0.5s;
}

.list li:hover {
  transform: translateX(8px);
  color: rgb(189, 135, 65);
  cursor: pointer;
}

.backdrop {
  width: 95%;
  height: 95%;
  border-radius: 25px;
  overflow-x: hidden;
  overflow-y: scroll;
  /* outline: 1px solid black; */
}

.backdrop::-webkit-scrollbar {
  background-color: transparent;
  width: 0.5em;
}

/* .backdrop::-webkit-scrollbar-track {
  box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
} */

.backdrop::-webkit-scrollbar-thumb {
  background-color: rgba(216, 216, 216, 0.44);
  border-radius: 25px;
  outline: 1px solid slategrey;
}

.introImg {
  position: relative;
  top: 10vh;
  width: 92%;
  height: 74%;
  border-radius: 25px;
  margin: auto;
  box-shadow: 0px 7px 12px 10px rgba(0, 0, 0, 0.62);
}

.introImg video {
  width: 100%;
  height: auto;
  border-radius: 25px;
}

.introVid {
  position: relative;
  top: 10vh;
  width: 92%;
  height: 74%;
  border-radius: 25px;
  margin: auto;
  box-shadow: 0px 7px 12px 10px rgba(0, 0, 0, 0.62);
}

.introVid video {
  width: 100%;
  height: auto;
  border-radius: 25px;
}

.footer {
  display: ;
}
</style>