<template>
  <v-row class="d-flex justify-center mt-4">
    <v-container fluid>
      <v-row class="pa-6">
        <v-col cols="12" sm="8">
          <h1>Nilout Blog</h1>
          <!-- <h1 class="typewriter nocaret"></h1> -->
          <p id="animated-text">ຮວບຮວມທຸກຜົນງານ</p>
          <v-btn class="outlined-button" outlined>Web Dev</v-btn>
          <v-btn class="outlined-button" outlined>Software Dev</v-btn>
          <v-btn class="outlined-button" outlined>Game Dev</v-btn>
          <v-btn class="outlined-button" outlined>UX/UI Design</v-btn>
          <v-btn class="outlined-button" outlined>Mobile Application Dev</v-btn>
          <p>By Nilout Stls</p>
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
      >
        <v-col
          cols="12"
          class="green lighten-2 fill-height d-flex flex-column justify-center align-center"
        >
          <v-card flat tile>
            <v-card-text>Card #1</v-card-text>
          </v-card>
        </v-col>
      </v-container>
    </v-container>
    <v-col cols="12" sm="8" md="3" v-for="item in items" :key="item.title">
      <v-card
        :loading="loading"
        class="item mx-auto my-12"
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

        <v-img :src="item.imageUrl"></v-img>

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

        <v-card-title>Tonight's availability</v-card-title>

        <v-card-text>
          <v-chip-group
            v-model="selection"
            active-class="deep-purple accent-4 white--text"
            column
          >
            <v-chip>5:30PM</v-chip>

            <v-chip>7:30PM</v-chip>

            <v-chip>8:00PM</v-chip>

            <v-chip>9:00PM</v-chip>
          </v-chip-group>
        </v-card-text>

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
export default {
  data() {
    return {
      loading: false,
      selection: 1,
      currentIndex: null,
      items: [
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

      setTimeout(() => (this.loading = false), 2000)
    },
  },
  mounted() {
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
    }, 2000) // Change text every 2 seconds
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
  transition: background-color 0.3s ease-in;
  margin: 5px;
}

.outlined-button:hover {
  margin: 5;
  background-color: #16b076;
  transform: scale(1.1);
  color: black;
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
@keyframes typing {
  0.0000%,
  27.3488% {
    content: '';
  }
  1.1395%,
  26.2093% {
    content: 'd';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  2.2791%,
  25.0698% {
    content: 'de';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  3.4186%,
  23.9302% {
    content: 'dev';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  4.5581%,
  22.7907% {
    content: 'deve';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  5.6977%,
  21.6512% {
    content: 'devel';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  6.8372%,
  20.5116% {
    content: 'develo';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  7.9767%,
  19.3721% {
    content: 'develop';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  9.1163%,
  18.2326% {
    content: 'develope';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  10.2558%,
  17.0930% {
    content: 'developer';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }

  30.7674%,
  51.2791% {
    content: '';
  }
  31.9070%,
  50.1395% {
    content: 'w';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  33.0465%,
  49.0000% {
    content: 'wr';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  34.1860%,
  47.8605% {
    content: 'wri';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  35.3256%,
  46.7209% {
    content: 'writ';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  36.4651%,
  45.5814% {
    content: 'write';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  37.6047%,
  44.4419% {
    content: 'writer';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }

  54.6977%,
  75.2093% {
    content: '';
  }
  55.8372%,
  74.0698% {
    content: 'r';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  56.9767%,
  72.9302% {
    content: 're';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  58.1163%,
  71.7907% {
    content: 'rea';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  59.2558%,
  70.6512% {
    content: 'read';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  60.3953%,
  69.5116% {
    content: 'reade';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  61.5349%,
  68.3721% {
    content: 'reader';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }

  78.6279%,
  96.8605% {
    content: '';
  }
  79.7674%,
  95.7209% {
    content: 'h';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  80.9070%,
  94.5814% {
    content: 'hu';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  82.0465%,
  93.4419% {
    content: 'hum';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  83.1860%,
  92.3023% {
    content: 'huma';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
  }
  84.3256%,
  91.1628% {
    content: 'human';
    color: #16b076;
    font-size: 72px;
    font-weight: bold;
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
