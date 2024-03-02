<template>
  <section id="about">
    <v-container fluid>
      <v-row align="center" justify="center">
        <v-col cols="10">
          <v-row align="center" justify="center">
            <v-col cols="12" md="7">
              <h1 class="font-weight-light display-2">About Me!</h1>
              <h1 class="font-weight-light display-1 mb-3">============</h1>
              <v-row>
                <v-col cols="12" class="d-flex align-center">
                  <v-img
                    :src="require('@/assets/images/icon3.svg')"
                    max-width="60px"
                    class="mr-4"
                    data-aos="fade-right"
                  />
                  <p class="text-justify" data-aos="fade-right">
                    I Would Love to make your Ideas real I love to make App and
                    Web Application by
                    Flutter,Vue.js/Nuxt.js,React.js/Next.js...and I would like
                    invent equipment about Internet of things.Now I'm join in
                    Community Champa Maker club for develop my skills and to
                    gain experience with everyone in community
                  </p>
                </v-col>
                <!-- <v-col cols="12" class="d-flex align-center">
                  <v-img
                    src="@/assets/img/icon2.svg"
                    max-width="60px"
                    class="mr-4"
                  />
                  <p class="text-justify">
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit.
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit.
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit.
                  </p>
                </v-col>
                <v-col cols="12" class="d-flex align-center">
                  <v-img
                    src="@/assets/img/icon3.svg"
                    max-width="60px"
                    class="mr-4"
                  />
                  <p class="text-justify">
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit.
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit.
                    Lorem ipsum dolor sit amet consectetur, adipisicing elit.
                  </p>
                </v-col> -->
              </v-row>
            </v-col>
            <v-col cols="12" md="5" class="d-none d-md-flex">
              <v-img
                :src="require('@/assets/images/mm.png')"
                class="d-block ml-auto mr-auto"
                max-width="400px"
                data-aos="fade-left"
              />
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>
<script>
import AOS from 'aos'
import 'aos/dist/aos.css'

export default {
  data() {
    return {}
  },
  mounted() {
    AOS.init()
  },
}
</script>
<style scoped>
#about {
  background-color: #f4f7f5;
}
</style>
