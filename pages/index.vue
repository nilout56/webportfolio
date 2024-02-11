<template>
  <v-row class="d-flex justify-center mt-4">
    <v-container fluid class="mt-4 mb-8">
      <v-row class="pa-6">
        <v-col cols="12" sm="8">
          <h1>Nilout Blog</h1>
          <!-- <h1 class="typewriter nocaret"></h1> -->
          <p id="animated-text">ຮວບຮວມທຸກຜົນງານ</p>
          <v-btn class="outlined-button" outlined>Web Dev</v-btn>
          <v-btn class="outlined-button" outlined>Software Dev</v-btn>
          <v-btn class="outlined-button" outlined>Game Dev</v-btn>
          <v-btn class="outlined-button" outlined>UX/UI Design</v-btn>
          <v-btn class="outlined-button" outlined>Mobile Application</v-btn>
        </v-col>
        <v-col cols="12" sm="4">
          <div class="space">
            <div class="sun"></div>
            <div class="earth">
              <div class="dino"></div>
              <div class="iconv"></div>
            </div>
          </div>
        </v-col>
      </v-row>
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
          :src="imageUrls[currentImageUrlIndex]"
          max-width="auto"
          cols="12"
        >
          <v-row align="center" justify="center">
            <v-col class="text-center" cols="12">
              <h1
                class="text-h4 font-weight-thin mb-4"
                data-aos="zoom-out-down"
              >
                Never Stop Learning
              </h1>
              <h4 class="subheading" data-aos="zoom-out">
                Follow And Make Your Dream❤️!
              </h4>
            </v-col>
          </v-row>
        </v-parallax>
        <h1 class="font-weight-bold mt-5 mb-12">ບົດຄວາມສຸດພິເສດ 🦖</h1>
      </v-container>
      <v-container cols="6" class="mt-12 mb-12"> </v-container>
    </v-container>
    <v-col cols="12" sm="8" md="3" v-for="item in items" :key="item.title">
      <v-card
        :loading="loading"
        class="item mx-auto my-12 mb-8"
        max-width="400"
        target="_blank"
        @mouseover="currentIndex = index"
        @mouseleave="currentIndex = null"
      >
        <template slot="progress">
          <v-progress-linear
            color="deep-purple"
            height="10"
            indeterminate
          ></v-progress-linear>
        </template>

        <v-img :src="item.imageUrl" max-width="400px" mx-height="200px"></v-img>

        <v-card-title>{{ item.title }}</v-card-title>

        <v-card-text>
          <v-row align="center" class="mx-0">
            <v-rating
              :value="4.5"
              color="amber"
              dense
              half-increments
              readonly
              size="14"
            ></v-rating>

            <div class="grey--text ms-4">4.5 (413)</div>
          </v-row>

          <div class="my-4 text-subtitle-1">{{ item.subtitle }}</div>

          <v-text>
            {{ item.text }}
          </v-text>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>

        <v-card-actions>
          <v-btn color="deep-purple lighten-2" text @click="reserve">
            Reserve
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import AOS from 'aos'
import 'aos/dist/aos.css'
export default {
  data() {
    return {
      loading: false,
      selection: 1,
      currentIndex: null,
      currentImageUrlIndex: 0,

      show: false,
      imageUrls: [
        'https://i.makeagif.com/media/9-18-2018/RySj_U.gif',
        'https://media0.giphy.com/media/JrZHAQT0CxmkPWj9LZ/200.gif',
        'https://i.gifer.com/J4o.gif',
        'https://i.gifer.com/VJi.gif',
      ],
      items: [
        {
          title: 'ສ້າງ card ດ້ວຍ vuetify ງ່າຍໆ',
          subtitle: 'ໂດຍ ນິລຸດ ເຮືອງແພງສີ',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl: require('@/assets/images/me.jpeg'),
          link: '#',
        },
        {
          title: 'ສ້າງ card ດ້ວຍ vuetify ງ່າຍໆ',
          subtitle: 'ໂດຍ ນິລຸດ ເຮືອງແພງສີ',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl: require('@/assets/images/meee.jpeg'),
          link: '#',
        },
        {
          title: 'ສ້າງ card ດ້ວຍ vuetify ງ່າຍໆ',
          subtitle: 'ໂດຍ ນິລຸດ ເຮືອງແພງສີ',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://occ-0-64-58.1.nflxso.net/dnm/api/v6/0DW6CdE4gYtYx8iy3aj8gs9WtXE/AAAABSxTd7UnypTYDX5rxc3b24el9YjrfnHShBgCvf41pKYaYeazzLqyr8DwzjitEVdPfY1UbzV0esVERoJTlKDHgOTfUQfgmU-mF8doZB2wNf0z9V9_xYqzwedxFjuB.jpg',
          link: '#',
        },
        {
          title: 'ສ້າງ card ດ້ວຍ vuetify ງ່າຍໆ',
          subtitle: 'ໂດຍ ນິລຸດ ເຮືອງແພງສີ',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://fancy-kid.com/wp-content/uploads/2020/03/AAAABUzjI_9C29BLVMlg4DnrRGgj8aiy-kAN0H-5ljMuNBzjdgpR51R8hEmpSgh805krsL3UaD6EtUoT5t04WRR9j2yc2-vR-1920x1080.jpg',
          link: '#',
        },
        {
          title: 'ສ້າງ card ດ້ວຍ vuetify ງ່າຍໆ',
          subtitle: 'ໂດຍ ນິລຸດ ເຮືອງແພງສີ',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://mpics.mgronline.com/pics/Images/563000003510401.JPEG',
          link: '#',
        },
        {
          title: 'ສ້າງ card ດ້ວຍ vuetify ງ່າຍໆ',
          subtitle: 'ໂດຍ ນິລຸດ ເຮືອງແພງສີ',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://4.bp.blogspot.com/--Z1nqbEOgLA/XQtZ0cdTchI/AAAAAAAAgOg/QAitEmvmu9U-WmiygAAjlDapKy8uRBUewCLcBGAs/s1600/rsz_dark2.jpg',
          link: '#',
        },
        {
          title: 'ສ້າງ card ດ້ວຍ vuetify ງ່າຍໆ',
          subtitle: 'ໂດຍ ນິລຸດ ເຮືອງແພງສີ',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://occ-0-64-58.1.nflxso.net/dnm/api/v6/0DW6CdE4gYtYx8iy3aj8gs9WtXE/AAAABSxTd7UnypTYDX5rxc3b24el9YjrfnHShBgCvf41pKYaYeazzLqyr8DwzjitEVdPfY1UbzV0esVERoJTlKDHgOTfUQfgmU-mF8doZB2wNf0z9V9_xYqzwedxFjuB.jpg',
          link: '#',
        },
        {
          title: 'การสร้าง Component เองใน Figma',
          subtitle: 'ໂດຍ ນິລຸດ ເຮືອງແພງສີ',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://fancy-kid.com/wp-content/uploads/2020/03/AAAABUzjI_9C29BLVMlg4DnrRGgj8aiy-kAN0H-5ljMuNBzjdgpR51R8hEmpSgh805krsL3UaD6EtUoT5t04WRR9j2yc2-vR-1920x1080.jpg',
          link: '#',
        },
        {
          title: 'การสร้าง Component เองใน Figma',
          subtitle: 'โดย ไกรศร แก้วเศรษฐี',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://mpics.mgronline.com/pics/Images/563000003510401.JPEG',
          link: '#',
        },
        {
          title: 'การสร้าง Component เองใน Figma',
          subtitle: 'โดย ไกรศร แก้วเศรษฐี',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://4.bp.blogspot.com/--Z1nqbEOgLA/XQtZ0cdTchI/AAAAAAAAgOg/QAitEmvmu9U-WmiygAAjlDapKy8uRBUewCLcBGAs/s1600/rsz_dark2.jpg',
          link: '#',
        },
        {
          title: 'การสร้าง Component เองใน Figma',
          subtitle: 'โดย ไกรศร แก้วเศรษฐี',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://occ-0-64-58.1.nflxso.net/dnm/api/v6/0DW6CdE4gYtYx8iy3aj8gs9WtXE/AAAABSxTd7UnypTYDX5rxc3b24el9YjrfnHShBgCvf41pKYaYeazzLqyr8DwzjitEVdPfY1UbzV0esVERoJTlKDHgOTfUQfgmU-mF8doZB2wNf0z9V9_xYqzwedxFjuB.jpg',
          link: '#',
        },
        {
          title: 'การสร้าง Component เองใน Figma',
          subtitle: 'โดย ไกรศร แก้วเศรษฐี',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://fancy-kid.com/wp-content/uploads/2020/03/AAAABUzjI_9C29BLVMlg4DnrRGgj8aiy-kAN0H-5ljMuNBzjdgpR51R8hEmpSgh805krsL3UaD6EtUoT5t04WRR9j2yc2-vR-1920x1080.jpg',
          link: '#',
        },
        {
          title: 'การสร้าง Component เองใน Figma',
          subtitle: 'โดย ไกรศร แก้วเศรษฐี',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://mpics.mgronline.com/pics/Images/563000003510401.JPEG',
          link: '#',
        },
        {
          title: 'การสร้าง Component เองใน Figma',
          subtitle: 'โดย ไกรศร แก้วเศรษฐี',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://4.bp.blogspot.com/--Z1nqbEOgLA/XQtZ0cdTchI/AAAAAAAAgOg/QAitEmvmu9U-WmiygAAjlDapKy8uRBUewCLcBGAs/s1600/rsz_dark2.jpg',
          link: '#',
        },
        {
          title: 'การสร้าง Component เองใน Figma',
          subtitle: 'โดย ไกรศร แก้วเศรษฐี',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://occ-0-64-58.1.nflxso.net/dnm/api/v6/0DW6CdE4gYtYx8iy3aj8gs9WtXE/AAAABSxTd7UnypTYDX5rxc3b24el9YjrfnHShBgCvf41pKYaYeazzLqyr8DwzjitEVdPfY1UbzV0esVERoJTlKDHgOTfUQfgmU-mF8doZB2wNf0z9V9_xYqzwedxFjuB.jpg',
          link: '#',
        },
        {
          title: 'การสร้าง Component เองใน Figma',
          subtitle: 'โดย ไกรศร แก้วเศรษฐี',
          text: 'การสร้างและใช้ Component เองใน...',
          imageUrl:
            'https://fancy-kid.com/wp-content/uploads/2020/03/AAAABUzjI_9C29BLVMlg4DnrRGgj8aiy-kAN0H-5ljMuNBzjdgpR51R8hEmpSgh805krsL3UaD6EtUoT5t04WRR9j2yc2-vR-1920x1080.jpg',
          link: '#',
        },
      ],
    }
  },
  methods: {
    reserve() {
      this.loading = true

      setTimeout(() => (this.loading = false), 5000)
    },
    updateParallaxImage() {
      this.currentImageUrlIndex =
        (this.currentImageUrlIndex + 1) % this.imageUrls.length
      const newImageUrl = this.imageUrls[this.currentImageUrlIndex]
      document.getElementById(
        'animated-parallax'
      ).style.backgroundImage = `url('${newImageUrl}')`
    },
  },
  mounted() {
    setInterval(this.updateParallaxImage, 3000)
    const texts = [
      'ເສີມສ້າງຄວາມຮູ້',
      'ເພີ່ມພູນຄວາມສາມາດ',
      'ພັດທະນາຊີວິດ',
      'ຄິດກ່ອນລົງມືທຳ',
      'ຂະຫຍັນແລະອົດທົນ',
    ]

    let count = 0

    setInterval(() => {
      document.getElementById('animated-text').innerHTML = texts[count]
      count = (count + 1) % texts.length
    }, 2000),
      AOS.init() // Change text every 2 seconds
  },
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
  background-image: url('~@/assets/images/icons-graphql.png');
  width: 60px;
  height: 40px;
  border-radius: 30px;
  margin: 0 auto;
  background-size: contain;
  position: relative;
  top: 20%;
  animation-name: spin, scale;
  animation-duration: 0.5s;
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
</style>
