<template>
  <v-row class="d-flex justify-center mt-4 ml-2 mb-6">
    <v-container fluid class="mt-4 mb-8">
      <v-row class="pa-0 justify-end">
        <v-col cols="12">
          <h1><gamebutton /></h1>

          <!-- <h1 class="typewriter nocaret"></h1> -->
          <!-- <p id="animated-text">ຮວບຮວມທຸກຜົນງານ</p> -->
          <v-btn class="outlined-button" outlined>Web Dev</v-btn>
          <v-btn class="outlined-button" outlined>Software Dev</v-btn>
          <v-btn class="outlined-button" outlined>Game Dev</v-btn>
          <v-btn class="outlined-button" outlined>UX/UI Design</v-btn>
          <v-btn class="outlined-button" outlined>Mobile Application</v-btn>
        </v-col>
        <v-col cols="12" md="6" sm="2">
          <div class="space">
            <div class="sun">
              <div class="planet"></div>
            </div>
            <div class="earth">
              <div class="dino"></div>
              <div class="iconv"></div>
            </div>
          </div>
        </v-col>
      </v-row>
    </v-container>

    <cardhover />

    <div>
      <detailss />
    </div>

    <v-container
      max-width="auto"
      align="center"
      justify="center"
      style="height: 50vh"
      dense
      elevation="0"
      class="mb-12 mt-6"
    >
      <v-parallax
        dark
        max-width="auto"
        cols="12"
        src="https://images.unsplash.com/photo-1524169220946-12efd782aab4?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D"
      >
        <v-row align="center" justify="center">
          <v-col class="text-center" cols="12">
            <h1 class="text-h4 font-weight-thin mb-4" data-aos="zoom-out-down">
              Never Stop Learning
            </h1>
            <spin />
            <h4 class="subheading" data-aos="zoom-out">
              Follow And Make Your Dream❤️!
            </h4>
          </v-col>
          <div class="svg-border-waves">
            <img src="@/assets/images/borderWaves.svg" />
          </div>
          <div class="svg-border-waves">
            <img src="@/assets/images/borderWavesBlue.svg" />
          </div>
        </v-row>
      </v-parallax>
    </v-container>

    <v-container> </v-container>
  </v-row>
</template>

<script>
import AOS from 'aos'
import 'aos/dist/aos.css'
import cardhover from '../components/hovercard/cardhover.vue'
import spacebutton from '../components/buttons/spacebutton.vue'
import gamebutton from '../components/buttons/gamebutton.vue'
import detailss from '../components/me.vue'
import spin from '../components/spin.vue'
export default {
  components: { cardhover, spacebutton, detailss, gamebutton, spin },
  data() {
    return {
      loading: false,
      selection: 1,
      currentIndex: null,
      currentImageUrlIndex: 0,

      show: false,
    }
  },
  methods: {},
}
</script>

<style scoped>
.item {
  transition: 0.3s ease;
  font-weight: bold;
}
.img-border {
  width: 350px;
  height: 200px;
}
.item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.item:hover {
  transform: scale(1.1);
}
.space {
  width: 300px;
  height: 300px;
  margin: 0 auto;
  border-radius: 100%;
  background-image: url('https://s.itl.cat/pngfile/s/287-2872261_holographic-wallpaper-hd-hologram.jpg');
  overflow: hidden;
  animation-name: spin;
  animation-duration: 100s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}
.sun {
  width: 60px;
  height: 40px;
  border-radius: 30px;
  margin: 0 auto;
  background-size: contain;
  position: relative;
  top: 20%;
  animation-name: spin;
  animation-duration: 100s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}
.earth {
  width: 250px;
  height: 250px;
  border-radius: 300px;

  background-image: url('https://www.borntodev.com/wp-content/uploads/2020/03/earth.png');
  margin: 0 auto;
  background-size: contain;
  animation-name: spin;
  animation-duration: 10s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  position: relative;
  top: 60%;
}
.dino {
  margin: 0 auto;
  background-image: url('~@/assets/images/icons-flutter.png');
  border-radius: 50px;
  background-size: contain;
  width: 75px;
  height: 65px;
  top: -5px;
  position: relative;

  animation-name: spin;
  animation-duration: 1s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  z-index: 2;
}
.iconv {
  margin: 0 auto;
  background-image: url('~@/assets/images/icons-nuxt.png');
  border-radius: 50px;
  background-size: contain;
  width: 90px;
  height: 75px;
  top: -10px;
  position: relative;

  animation-name: spin;
  animation-duration: 5s;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
  z-index: -2;
}
.outlined-button {
  /* transition: background-color 0.3s ease-in; */
  margin: 5px;
  font-weight: 700;
  border-radius: 0;
  text-transform: uppercase;
  overflow: hidden;
  position: relative;
}
.outlined-button::before {
  content: '';
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(120deg, transparent, #00fffc, transparent);
  transform: translateX(-100%);
  transition: 0.6s;
  position: absolute;
}
.outlined-button:hover {
  margin: 5;
  background: transparent;
  box-shadow: 0 0 20px 5px #00fffc;
  transform: scale(1.1);
  font-weight: bold;
}

@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
@keyframes scale {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(0.8);
  }
  100% {
    transform: scale(1);
  }
}

#animated-text {
  animation: fade 2s infinite;
}

@keyframes fade {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

@keyframes blink {
  0%,
  100% {
    opacity: 1;
  }
  50% {
    opacity: 0;
  }
}

.typewriter {
  --caret: currentcolor;
}

.typewriter::before {
  content: '';
  animation: typing 13.5s infinite;
}

.typewriter::after {
  content: '';
  border-right: 1px solid var(--caret);
  animation: blink 0.5s linear infinite;
}

.typewriter.thick::after {
  border-right: 1ch solid var(--caret);
}

.typewriter.nocaret::after {
  border-right: 0;
}

@media (prefers-reduced-motion) {
  .typewriter::after {
    animation: none;
  }

  @keyframes sequencePopup {
    0%,
    100% {
      content: 'developer';
    }
    25% {
      content: 'writer';
    }
    50% {
      content: 'reader';
    }
    75% {
      content: 'human';
    }
  }

  .typewriter::before {
    content: 'developer';
    animation: sequencePopup 12s linear infinite;
  }
}
.planet {
  display: block;
  width: 50px;
  height: 55px;
  position: relative;
  transform-style: preserve-3d;
  border-radius: 50%;
  background: #fcc96b;
  background: #fcc96b;
  background: linear-gradient(
    180deg,
    #fcc96b 0%,
    #fcc96b 15%,
    #f7ae01 15%,
    #f7ae01 19%,
    #fcc96b 19%,
    #fcc96b 22%,
    #f7ae01 22%,
    #f7ae01 28%,
    #fcc96b 28%,
    #fcc96b 31%,
    #fcc96b 33%,
    #fcc96b 36%,
    #f7ae01 36%,
    #f7ae01 48%,
    #fcc96b 48%,
    #fcc96b 55%,
    #f7ae01 55%,
    #f7ae01 66%,
    #fcc96b 66%,
    #fcc96b 70%,
    #f7ae01 70%,
    #f7ae01 73%,
    #fcc96b 73%,
    #fcc96b 82%,
    #f7ae01 82%,
    #c7ba9d 86%,
    #fcc96b 86%
  );
  box-shadow: inset 0 0 25px rgba(0, 0, 0, 0.25),
    inset 8px -4px 6px rgba(199, 128, 0, 0.5),
    inset -8px 4px 8px rgba(255, 235, 199, 0.5), inset 20px -5px 12px #f7ae01,
    0 0 100px #ffffff59;
  transform: rotateZ(-15deg);
}

.planet::before {
  position: absolute;
  content: '';
  display: block;
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  border: 16px solid #e1a519;
  border-top-width: 0;
  border-radius: 50%;
  box-shadow: 0 -2px 0 #c18620;
  animation: rings1 0.8s infinite linear;
}

.planet::after {
  position: absolute;
  content: '';
  display: block;
  width: 100%;
  height: 100%;
  box-sizing: border-box;
  border: 8px solid #d48b0c;
  border-top-width: 0;
  border-radius: 50%;
  box-shadow: 0 -2px 0 #b99309;
  animation: rings2 0.8s infinite linear;
}

@keyframes rings1 {
  0% {
    transform: rotateX(65deg) rotateZ(0deg) scale(1.75);
  }

  100% {
    transform: rotateX(65deg) rotateZ(360deg) scale(1.75);
  }
}

@keyframes rings2 {
  0% {
    transform: rotateX(65deg) rotateZ(0deg) scale(1.7);
  }

  100% {
    transform: rotateX(65deg) rotateZ(360deg) scale(1.7);
  }
}
</style>
