<template>
  <v-app>
    <!-- <v-navigation-drawer
      :mini-variant.sync="miniVariant"
      :mini-variant-width="70"
      :width="250"
      v-model="drawer"
      fixed
      app
      :clipped="clipped"
    >
      <v-list class="mx-2" v-if="drawer === true">
        <v-list-item>
          <v-list-item-content>
            <div class="d-flex justify-end">
              <v-icon @click.stop="miniVariant = !miniVariant"
                >mdi-{{
                  `${
                    miniVariant ? 'chevron-double-right' : 'chevron-double-left'
                  }`
                }}</v-icon
              >
            </div>
          </v-list-item-content>
        </v-list-item>
      </v-list>

      <v-list class="mx-2">
        <template v-for="(item, index) in items">
          <v-subheader
            v-show="!miniVariant"
            v-if="item.header"
            :key="item.header"
            inset
          >
            {{ item.header }}
          </v-subheader>
          <v-divider v-else-if="item.divider" :key="index" inset></v-divider>
          <v-list-item
            v-else
            :key="item.title"
            :to="item.to"
            active-class="blue--text"
            ripple
            :title="item.title"
          >
            <v-list-item-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-action>
            <v-list-item-content>
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </template>
      </v-list>
    </v-navigation-drawer> -->

    <v-app-bar elevation="0" :clipped-left="clipped" fixed app hide-on-scroll>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer"> </v-app-bar-nav-icon>

      <v-spacer />
      <v-switch
        v-model="$vuetify.theme.dark"
        inset
        label="ປ່ຽນໂໝດ"
        persistent-hint
      ></v-switch>
    </v-app-bar>
    <v-main class="main">
      <div>
        <Nuxt />
      </div>
    </v-main>
    <foot />
    <v-btn
      v-show="fab"
      v-scroll="onScroll"
      id="print"
      fab
      dark
      fixed
      bottom
      right
      color="primary"
      @click="toTop"
    >
      <v-icon> mdi-chevron-up</v-icon>
    </v-btn>
  </v-app>
</template>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+Lao+Looped:wght@200&family=Noto+Sans+Lao:wght@200;400&display=swap');

* {
  /* font-family: 'Noto Sans Lao', sans-serif; */
  font-family: 'Noto Sans Lao Looped', sans-serif;
  font-weight: 500;
}
.blue--text {
  color: white !important;
  background: linear-gradient(90deg, #14746f 2.23%, #67b99a 100%);
  border-radius: 6px;
}
.v-navigation-drawer >>> .v-navigation-drawer__border {
  display: none;
}
.v-main {
  background-image: url('@/assets/images/bgMain.png');
  background-attachment: fixed;
  background-position: center;
  background-size: cover;
}
</style>
<script>
import foot from '../components/footer.vue'
export default {
  components: { foot },
  name: 'DefaultLayout',

  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      locale: '',
      fab: false,
      items: [
        {
          icon: 'mdi-view-dashboard-edit',
          title: 'Dashboard',
          to: '/',
        },
        {
          icon: 'mdi-apple',
          title: 'Apple',
          to: '/home_service',
        },
        {
          icon: 'mdi-android',
          title: 'Android',
          to: '/mapbox/display-one',
        },
        {
          icon: 'mdi-archive-cog-outline',
          title: 'Archive',
          to: '/mapbox/marker',
        },
        {
          icon: 'mdi-chart-bell-curve',
          title: 'ApexCharts',
          to: '/apexchart/chart',
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: '',
    }
  },
  methods: {
    onScroll(e) {
      if (typeof window === 'undefined') return
      const top = window.pageYOffset || e.target.scrollTop || 0
      this.fab = top > 500
    },
    toTop() {
      this.$vuetify.goTo(0)
    },
  },
}
</script>
