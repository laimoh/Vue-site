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
              Just a creator and designer attemping to connect
              <span>⥃</span>
              our tangible
              <span>▪</span> and intangible <span>✧</span> worlds.
              <br />
              <br />Currently residing in London, UK.
            </h1>
          </div>
          <ul>
            <li @click="openSpeech"><span>☞</span> Typed Speech</li>
            <li @click="openWindPoetry"><span>☞</span> Wind Poetry</li>
            <li @click="openRec">
              <span>☞</span> Would You Like <br />A Receipt?
            </li>
            <li @click="openShek"><span>☞</span> Shek Leung</li>
            <li @click="openIL"><span>☞</span> Invisible Lines</li>
            <li @click="openYB"><span>☞</span> Yazdani Bakery</li>
          </ul>
        </div>
      </div>
    </div>
    <div class="gradient">
      <div style="width: 97%;" class="project container">
        <!-- <div v-if="showCnv" class="container border"> -->
        <transition name="fade">
          <div v-if="showCnv" id="p5Canvas"></div>
        </transition>
        <!-- </div> -->
        <transition name="fade">
          <div
            v-if="showSpeech"
            class="backdrop"
            @scroll.passive="handleScroll"
          >
            <Header
              theme="TS"
              header="Typed Speech"
              subhead="(Ongoing)"
              :types="['Generative Design Tool', 'Voice Visualisation', '2020']"
            ></Header>
            <div class="sitelink">
              <a href="https://sonic-type.glitch.me/">Working Site ↗</a>
            </div>
            <div class="TS-introVid top">
              <video controls src="../public/assets/type/intro.mp4"></video>
            </div>
            <BodyText
              theme="TS"
              heading="ABOUT"
              body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Etiam consequat, massa ut consequat lacinia, velit dui molestie dolor, id dapibus sem justo a ante. In pellentesque, odio ut pharetra congue, quam tellus efficitur arcu, non mattis risus nibh ac turpis."
            ></BodyText>
            <div class="TS-vidGallery">
              <div class="TS-vidDemo">
                <video
                  @mouseover="focusVid"
                  @mouseleave="unfocusVid"
                  src="../public/assets/type/iswhatitis3.mp4"
                ></video>
              </div>
              <div class="TS-vidDemo">
                <video
                  @mouseover="focusVid"
                  @mouseleave="unfocusVid"
                  src="../public/assets/type/hi-there.mp4"
                ></video>
              </div>
              <div class="TS-vidDemo">
                <video
                  @mouseover="focusVid"
                  @mouseleave="unfocusVid"
                  src="../public/assets/type/g-afternoon.mp4"
                ></video>
              </div>
              <div class="TS-vidDemo">
                <video
                  @mouseover="focusVid"
                  @mouseleave="unfocusVid"
                  src="../public/assets/type/xcuse.mp4"
                ></video>
              </div>
              <div class="TS-vidDemo">
                <video
                  @mouseover="focusVid"
                  @mouseleave="unfocusVid"
                  src="../public/assets/type/interesting.mp4"
                ></video>
              </div>
              <div class="TS-vidDemo">
                <video
                  @mouseover="focusVid"
                  @mouseleave="unfocusVid"
                  src="../public/assets/type/wonder.mp4"
                ></video>
              </div>
              <div class="TS-vidDemo">
                <video
                  @mouseover="focusVid"
                  @mouseleave="unfocusVid"
                  src="../public/assets/type/ladybird2.mp4"
                ></video>
              </div>
              <div class="TS-vidDemo">
                <video
                  @mouseover="focusVid"
                  @mouseleave="unfocusVid"
                  src="../public/assets/type/tea.mp4"
                ></video>
              </div>
            </div>
            <BodyText
              theme="REC"
              heading="PROCESS"
              body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Etiam consequat, massa ut consequat lacinia, velit dui molestie dolor, id dapibus sem justo a ante. In pellentesque, odio ut pharetra congue, quam tellus efficitur arcu, non mattis risus nibh ac turpis."
            ></BodyText>
            <Carousel @next="next" @prev="prev">
              <CarouselSlide
                v-for="(slide, index) in process.TS"
                :key="slide"
                :index="index"
                :visibleSlide="process.visibleSlide"
              >
                <img :src="slide" />
              </CarouselSlide>
            </Carousel>
            <!-- <img alt="page 1" :src="process.TS[0]" /> -->
          </div>
        </transition>
        <transition name="fade">
          <div v-if="showWP" class="backdrop" @scroll.passive="handleScroll">
            <Header
              theme="WP"
              header="Wind Poetry"
              :types="['Interaction', 'Data Visualisation', '2020']"
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
                src="../public/assets/wind/wind_poetry-demo-1.mp4"
              ></video>
            </div>
            <BodyText
              theme="WP"
              heading="PROCESS"
              body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Vivamus lobortis sapien porttitor, molestie urna ut, varius neque. In eu dapibus lectus. Etiam consequat, massa ut consequat lacinia, velit dui molestie dolor, id dapibus sem justo a ante. In pellentesque, odio ut pharetra congue, quam tellus efficitur arcu, non mattis risus nibh ac turpis."
            ></BodyText>
            <div class="introVid">
              <video
                controls
                src="../public/assets/wind/wind_poetry-demo.mp4"
              ></video>
            </div>
            <BodyText theme="WP" heading="TOOLS" body="✧ p5.js"></BodyText>
          </div>
        </transition>
        <transition name="fade">
          <div v-if="showRec" class="backdrop" @scroll.passive="handleScroll">
            <Header
              theme="REC"
              header="Would you like a receipt?"
              :types="['Chrome Extension', 'Data Visualisation', '2020']"
            ></Header>
            <div class="introVid top">
              <video
                autoplay
                controls
                src="../public/assets/reciept/analyzer-promo-film_ig.mp4"
              ></video>
            </div>
            <BodyText
              theme="REC"
              heading="ABOUT"
              body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Vivamus lobortis sapien porttitor, molestie urna ut, varius neque. In eu dapibus lectus. Etiam consequat, massa ut consequat lacinia, velit dui molestie dolor, id dapibus sem justo a ante. In pellentesque, odio ut pharetra congue, quam tellus efficitur arcu, non mattis risus nibh ac turpis."
            ></BodyText>
            <div class="introVid adjust">
              <video
                loop
                autoplay
                src="../public/assets/reciept/demo-main.mp4"
              ></video>
            </div>
            <BodyText
              theme="REC"
              heading="PROCESS"
              body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Vivamus lobortis sapien porttitor, molestie urna ut, varius neque. In eu dapibus lectus. Etiam consequat, massa ut consequat lacinia, velit dui molestie dolor, id dapibus sem justo a ante. In pellentesque, odio ut pharetra congue, quam tellus efficitur arcu, non mattis risus nibh ac turpis."
            ></BodyText>
            <div class="rec-vid-wrapper">
              <div class="rec-vid-container">
                <video
                  loop
                  autoplay
                  src="../public/assets/reciept/demo0.mp4"
                ></video>
              </div>
              <div class="rec-vid-container">
                <video
                  loop
                  autoplay
                  src="../public/assets/reciept/demo1.mp4"
                ></video>
              </div>
              <div class="rec-vid-container">
                <video
                  loop
                  autoplay
                  src="../public/assets/reciept/demo2.mp4"
                ></video>
              </div>
            </div>
            <BodyText theme="WP" heading="TOOLS" body="✧ p5.js"></BodyText>
          </div>
        </transition>
        <transition name="fade">
          <div v-if="showShek" class="backdrop" @scroll.passive="handleScroll">
            <Header
              theme="SH"
              header="Shek Leung"
              :types="['Web Development', 'Identity Design', '2020']"
            ></Header>
            <BodyText
              theme="SL"
              heading="ABOUT"
              body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Vivamus lobortis sapien porttitor, molestie urna ut, varius neque. In eu dapibus lectus. Etiam consequat, massa ut consequat lacinia, velit dui molestie dolor, id dapibus sem justo a ante. In pellentesque, odio ut pharetra congue, quam tellus efficitur arcu, non mattis risus nibh ac turpis."
            ></BodyText>
          </div>
        </transition>
        <transition name="fade">
          <div v-if="showIL" class="backdrop" @scroll.passive="handleScroll">
            <Header
              theme="IL"
              header="Invisible Lines"
              :types="['UX/UI', 'Campaign & Identity Design', '2020']"
            ></Header>
            <BodyText
              theme="IL"
              heading="ABOUT"
              body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Vivamus lobortis sapien porttitor, molestie urna ut, varius neque. In eu dapibus lectus. Etiam consequat, massa ut consequat lacinia, velit dui molestie dolor, id dapibus sem justo a ante. In pellentesque, odio ut pharetra congue, quam tellus efficitur arcu, non mattis risus nibh ac turpis."
            ></BodyText>
            <Video
              theme="IL"
              :vidSrc="require(`./assets/invi-lines/${srcIL.vid}`)"
            ></Video>
            <div class="wrap-align">
              <Image
                theme="subtext"
                :imgSrc="require(`./assets/invi-lines/${srcIL.imgs[3]}`)"
              ></Image>
              <Image
                theme="subtext"
                :imgSrc="require(`./assets/invi-lines/${srcIL.imgs[2]}`)"
              ></Image>
            </div>
            <div class="text-aligner">
              <BodyText
                theme="subtext"
                heading="APP"
                body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Vivamus lobortis sapien porttitor, molestie urna ut, varius neque."
              ></BodyText>
              <BodyText
                theme="reverse"
                heading="APP"
                body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus. Vivamus lobortis sapien porttitor, molestie urna ut, varius neque."
              ></BodyText>
            </div>
            <Image
              theme="IL"
              :imgSrc="require(`./assets/invi-lines/${srcIL.imgs[0]}`)"
            ></Image>
            <div class="text-aligner">
              <BodyText
                theme="subtext"
                heading="POSTER"
                body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placerat, non ultricies dui faucibus."
              ></BodyText>
              <BodyText
                theme="reverse"
                heading="VINYL COVER"
                body="Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam nulla magna, consectetur quis tellus eget, ultricies mattis nisi. Duis dictum dolor in ante placeraid dapibus sem justo a ante.."
              ></BodyText>
            </div>
            <Image
              theme="noshadow"
              :imgSrc="require(`./assets/invi-lines/${srcIL.imgs[1]}`)"
            ></Image>
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
// import P5 from "p5";
import Header from "./components/Header.vue";
import Gradient from "./components/Gradient.vue";
import BodyText from "./components/BodyText.vue";
import Carousel from "./components/Carousel.vue";
import CarouselSlide from "./components/CarouselSlide.vue";
import Video from "./components/Video.vue";
import Image from "./components/Image.vue";

export default {
  name: "App",
  components: {
    Header,
    Gradient,
    BodyText,
    Carousel,
    CarouselSlide,
    Video,
    Image
  },
  data() {
    return {
      process: {
        TS: [
          require("../public/assets/slides/process-TS-1.jpg"),
          require("../public/assets/slides/process-TS-2.jpg"),
          require("../public/assets/slides/process-TS-3.jpg"),
          require("../public/assets/slides/process-TS-4.jpg"),
          require("../public/assets/slides/process-TS-5.jpg"),
          require("../public/assets/slides/process-TS-6.jpg"),
          require("../public/assets/slides/process-TS-7.jpg")
        ],
        visibleSlide: 0
      },
      srcIL: {
        vid: "invisible-lines-film.mp4",
        imgs: [
          "POSTER_IL.jpg",
          "VINYL-COVER.png",
          "APP_IL_2.png",
          "APP_IL_1.png"
        ]
      },
      showCnv: true,
      showWP: false,
      showRec: false,
      showSpeech: false,
      showShek: false,
      showIL: false
    };
  },
  mounted() {
    if (this.showCnv) {
      const script = function(p5) {
        let numOfPoints = 200;
        let spacing, initialPosX, initialPosY;
        let time = 0;
        let time2 = 0;

        let posHistory = [];

        p5.setup = _ => {
          let canvas = p5.createCanvas(1000, 700);
          canvas.parent("p5Canvas");
          canvas.style("border-radius", "25px");
          initialPosX = 500;
          initialPosY = 350;
          spacing = 1.5;
        };

        const wave = (num, amp, freq) => {
          // your method
          return amp * p5.sin((freq * p5.TWO_PI * num) / numOfPoints + time);
        };

        const savePoints = () => {
          let phistory = [];
          let mappedY = Math.floor(p5.map(p5.mouseY, 0, p5.height, 5, 100));
          let mappedX = Math.floor(p5.map(p5.mouseX, 0, p5.width, 5, 30));

          for (let i = 0; i < numOfPoints; i++) {
            let angle = (p5.TWO_PI * i) / numOfPoints;
            let r = 250 + wave(i, mappedX, 10) + wave(i, mappedY, 3);
            // let r2 = 150 + wave(i, mappedY, 3) + wave(i, mappedY, 7);
            let x = initialPosX + r * p5.cos(angle);
            let y = initialPosY + r * p5.sin(angle);
            let v = p5.createVector(x, y);
            phistory.push(v);
          }
          return phistory;
        };

        const getPosHistory = () => {
          let p = savePoints();
          posHistory.push(p);

          if (posHistory.length > 5) {
            posHistory.shift();
          }
        };

        p5.draw = _ => {
          getPosHistory();

          for (let i = 0; i < posHistory.length; i++) {
            let pos = posHistory[i]; // an array of 25 positions of the whole shape

            for (let j = 0; j < pos.length; j++) {
              //   p5.noStroke();
              //   p5.fill(60, 50, 2);
              p5.blendMode(p5.EXCLUSION);
              p5.noFill();
              p5.stroke(35, 23, 48);
              p5.point(pos[j].x, pos[j].y);
             
            }
          }
          time = time + 0.05;
        };
      };

      const P5 = require("p5");
      new P5(script);
    }
  },
  methods: {
    closeProjects() {
      this.showCnv = false;
      this.showWP = false;
      this.showRec = false;
      this.showSpeech = false;
      this.showShek = false;
      this.showIL = false;
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
    },
    focusVid(e) {
      let srcVid = e.srcElement;
      srcVid.classList.add("focused");
      srcVid.play();
    },
    unfocusVid(e) {
      let srcVid = e.srcElement;
      srcVid.classList.remove("focused");
    },
    next() {
      if (this.process.visibleSlide >= this.process.TS.length - 1) {
        this.process.visibleSlide = 0;
      } else {
        this.process.visibleSlide++;
      }
      console.log(this.process.visibleSlide);
    },
    prev() {
      console.log("prev");
      if (this.process.visibleSlide <= 0) {
        this.process.visibleSlide = this.process.TS.length - 1;
      } else {
        this.process.visibleSlide--;
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
.focused {
  transform: scale(1.1, 1.2);
}

video:focus {
  outline: none;
}

.blend {
  mix-blend-mode: difference;
}

.TS-vidDemo audio {
  width: 100%;
  height: 50%;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease-out !important;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0 !important;
}

.center {
  margin: auto;
}

canvas {
  border-radius: 20px;
}

.sitelink {
  position: relative;
  top: 15vh;
  left: 50vw;
  width: 20vw;
  display: flex;
  justify-content: center;
  align-items: center;
}

.sitelink a {
  font-family: "Roboto Mono", monospace;
  color: white;
  font-size: 13px;
  font-weight: normal;
  text-decoration: none;
  color: white;
  cursor: pointer;
  padding: 0.8rem 0.8rem;
  border: solid 0.5px white;
  border-radius: 25px;
  transition: all 0.5s ease;
}

.sitelink a:hover {
  color: var(--yellow-text-color);
  border: solid 0.5px var(--yellow-text-color);
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
  font-size: 13px;
  font-weight: normal;
  margin-bottom: 2rem;
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
  margin-left: -2rem;
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

.TS-introVid {
  position: relative;
  top: 15vh;
  width: 92%;
  height: 72%;
  border-radius: 25px;
  margin: auto;
}

.TS-introVid video {
  box-shadow: 0px 7px 12px 10px rgba(0, 0, 0, 0.62);
}

.TS-vidGallery {
  /* outline: solid 1px black; */
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  margin: auto;
  width: 65vw;
  height: 100vh;
}

.TS-vidDemo {
  /* outline: solid 1px green; */
  width: 45%;
}

.TS-vidDemo video {
  width: 100%;
  height: auto;
  border-radius: 15px;
  box-shadow: 0px 5px 7px 4px rgba(0, 0, 0, 0.62);
  transition: all 0.5s ease;
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

.wrap-align {
  display: flex;
  width: 64vw;
  /* justify-content: space-evenly; */
  margin: auto;
}

.text-aligner {
  display: flex;
}

/* 
.img-heading {
  position: relative;
  font-family: "Roboto Mono", monospace;
  color: rgb(211, 211, 210);
  font-size: 11px;
  font-weight: normal;
  writing-mode: tb-rl;
  transform: rotate(-180deg);
  padding: 2rem 0.2rem;
  border: solid 0.5px rgb(211, 211, 210);
  border-radius: 25px;
} */
</style>
