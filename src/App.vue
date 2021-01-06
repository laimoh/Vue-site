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
          <div class="title">
            <!-- <h1 @click="closeProjects">{{ title }}</h1> -->
            <h1>
              Just a
              creator and designer attemping to connect
              <span>⥃</span>
              our
              tangible
              <span>▪</span> and
              intangible
              <span>✧</span> worlds.
              <br />
              <br />Currently residing in London.
            </h1>
          </div>
          <ul>
            <li @click="openWindPoetry">
              <span>☞</span> Wind Poetry
            </li>
            <li @click="openRec">
              <span>☞</span> Would You Like
              <br />A Receipt?
            </li>
            <li @click="openSpeech">
              <span>☞</span> Typed Speech
            </li>
            <li @click="openShek">
              <span>☞</span> Shek Leung
            </li>
            <li @click="openIL">
              <span>☞</span> Invisible Lines
            </li>
            <li @click="openYB">
              <span>☞</span> Yazdani Bakery
            </li>
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
          <div v-if="showRec" class="backdrop" @scroll.passive="handleScroll">
            <Header
              theme="REC"
              header="Would you like a receipt?"
              :types="['Chrome Extension','Data Visualisation','2020']"
            ></Header>
            <div class="introVid top">
              <video controls src="./assets/reciept/analyzer-promo-film_ig.mp4"></video>
            </div>
            <BodyText
              theme="REC"
              heading="ABOUT"
              body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Vivamus lobortis sapien porttitor, molestie urna ut, varius neque. In eu dapibus lectus. Etiam consequat, massa ut consequat lacinia, velit dui molestie dolor, id dapibus sem justo a ante. In pellentesque, odio ut pharetra congue, quam tellus efficitur arcu, non mattis risus nibh ac turpis."
            ></BodyText>
            <div class="introVid adjust">
              <video loop autoplay src="./assets/reciept/demo-main.mp4"></video>
            </div>
            <BodyText
              theme="REC"
              heading="PROCESS"
              body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Vivamus lobortis sapien porttitor, molestie urna ut, varius neque. In eu dapibus lectus. Etiam consequat, massa ut consequat lacinia, velit dui molestie dolor, id dapibus sem justo a ante. In pellentesque, odio ut pharetra congue, quam tellus efficitur arcu, non mattis risus nibh ac turpis."
            ></BodyText>
            <div class="rec-vid-wrapper">
              <div class="rec-vid-container">
                <video loop autoplay src="./assets/reciept/demo0.mp4"></video>
              </div>
              <div class="rec-vid-container">
                <video loop autoplay src="./assets/reciept/demo1.mp4"></video>
              </div>
              <div class="rec-vid-container">
                <video loop autoplay src="./assets/reciept/demo2.mp4"></video>
              </div>
            </div>
            <BodyText theme="WP" heading="TOOLS" body="✧ p5.js"></BodyText>
          </div>
        </transition>
        <transition name="fade">
          <div v-if="showSpeech" class="backdrop" @scroll.passive="handleScroll">
            <Header
              theme="SP"
              header="Typed Speech"
              :types="['Generative Design Tool','Voice Visualisation','2020']"
            ></Header>
          </div>
        </transition>
        <transition name="fade">
          <div v-if="showShek" class="backdrop" @scroll.passive="handleScroll">
            <Header
              theme="SH"
              header="Shek Leung"
              :types="['Web Development','Identity Design','2020']"
            ></Header>
          </div>
        </transition>
        <transition name="fade">
          <div v-if="showIL" class="backdrop" @scroll.passive="handleScroll">
            <Header
              theme="IL"
              header="Invisible Lines"
              :types="['UX/UI','Campaign & Identity Design','2020']"
            ></Header>
            <Video theme="IL" :vidSrc="srcIL"></Video>
            <div class="introVid top">
              <video controls src="/assets/invisible/invisible-lines-film.mp4"></video>
            </div>
            <img src="assets/invisible/.ig app_Social Media Art 1.png.icloud" />
          </div>
        </transition>
        <!-- <transition name="fade">
          <div v-if="showYB" class="backdrop" @scroll.passive="handleScroll">
            <Header
              theme="YB"
              header="Yazdani Bakery"
              :types="['Brand Identity Design','Publication Design','2019']"
            ></Header>
          </div>
        </transition>-->
      </div>
    </div>
    <Gradient>
      <template v-slot:footer>
        <h1 style="margin-top:10vh;">Laiqa Mohid</h1>
        <h1 style="margin-top:20vh;">©2021</h1>
      </template>
    </Gradient>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Gradient from "./components/Gradient.vue";
import BodyText from "./components/BodyText.vue";
import Video from "./components/Video.vue";

export default {
  name: "App",
  components: {
    Header,
    Gradient,
    BodyText,
    Video
  },
  data() {
    return {
      srcIL: "./assets/reciept/demo0.mp4",
      showWP: false,
      showRec: false,
      showSpeech: false,
      showShek: false,
      showIL: false
    };
  },
  methods: {
    closeProjects() {
      // this.title = "LIST OF WORKS";
      this.showWP = false;
      this.showRec = false;
      this.showSpeech = false;
      this.showShek = false;
      this.showIL = false;
      // this.showYB = false;
    },
    openWindPoetry() {
      this.closeProjects();
      setTimeout(() => {
        this.showWP = true;
      }, 800);
    },
    openRec() {
      this.closeProjects();
      setTimeout(() => {
        this.showRec = true;
      }, 800);
    },
    openSpeech() {
      this.closeProjects();
      setTimeout(() => {
        this.showSpeech = true;
      }, 800);
    },
    openShek() {
      this.closeProjects();
      setTimeout(() => {
        this.showShek = true;
      }, 800);
    },
    openIL() {
      this.closeProjects();
      setTimeout(() => {
        this.showIL = true;
      }, 800);
    },
    //  openYB() {
    //    this.closeProjects();
    //    setTimeout(() => {
    //      this.showYB = true;
    //    }, 800);
    //  },
    handleScroll(e) {
      var scrollPos = e.target.scrollTop;
      let h = document.querySelector(".header");
      if (scrollPos > 1) {
        h.classList.add("blend");
      } else {
        h.classList.remove("blend");
      }
    }
  }
};
</script>

<style scoped>
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

.fade-enter-from,
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
  color: var(--yellow-text-color);
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 18px;
  font-weight: normal;
  padding: 0px 10px;
  cursor: pointer;
}

.contact h1:hover {
  color: var(--yellow-text-color);
  border: solid 1px var(--yellow-text-color);
  transition: all ease 0.2s;
}

.list {
  height: 85%;
  width: 80%;
  list-style: none;
  display: flex;
  flex-direction: column;
  border-radius: 25px;
  justify-content: flex-start;
  align-items: center;
}

.title {
  text-align: right;
}

.title h1 {
  font-family: "Space Mono", monospace;
  color: var(--yellow-text-color);
  font-size: 12px;
  font-weight: normal;
  margin-bottom: 3rem;
  transition: all ease 0.2s;
}

.title h1 span {
  /* text-decoration: underline; */
  color: var(--orange-text-color);
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  font-family: "Space Mono", monospace;
  color: var(--yellow-text-color);
  font-size: 13px;
  white-space: nowrap;
}

ul li span {
  color: rgb(189, 135, 65);
  font-size: 1.6rem;
}

.indent {
  margin-left: 1rem;
}

.list li {
  margin: 1rem 0rem;
  transition: all 0.5s;
}

.list li:hover {
  transform: translateX(8px);
  color: var(--orange-text-color);
  cursor: pointer;
}

.backdrop {
  /* position: absolute; */
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

video {
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

.top {
  top: 20vh;
  margin-bottom: 20vh;
}

.intro-vid-wrapper {
  width: 40%;
  height: 40vh;
  display: flex;
  justify-content: space-evenly;
}

.adjust {
  height: 79%;
  top: 0vh;
}

.rec-vid-wrapper {
  width: 65vw;
  display: flex;
  justify-content: space-evenly;
  margin: auto;
}

.rec-vid-container {
  width: 19vw;
  display: flex;
  justify-content: center;
  align-items: center;
}

.rec-vid-container video {
  border-radius: 0px;
}
</style>