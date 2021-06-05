<template>
  <v-navigation-drawer
    v-model="drawer"
    app
    temporary
    disable-resize-watcher
    color="grey lighten-4"
  >
    {{ elArr }}
  </v-navigation-drawer>
</template>

<script>
/* eslint-disable no-console */
import { EventBus } from '@/event-bus'
// import _ from 'lodash'
// eslint-disable-next-line no-unused-vars

export default {
  data: () => ({
    drawer: false,
    items: null,
    elArr: null,
  }),
  async created() {},
  mounted() {
    const els = document.querySelectorAll('h2, h3')
    console.log(els)

    EventBus.$on('toggleSidebar', () => {
      console.log('toggle sidebar')
      this.drawer = !this.drawer
    })
    EventBus.$on('closeSidebar', () => {
      console.log('close sidebar')
      this.drawer = false
    })
  },
  methods: {
    routeToPage(item) {
      // console.log(item);
      this.drawer = false
      this.$router.push(`${item.path}/`).catch(() => {
        this.$vuetify.goTo(0)
      })
    },
  },
}
</script>
