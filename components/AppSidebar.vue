<template>
  <v-navigation-drawer
    v-model="drawer"
    app
    temporary
    disable-resize-watcher
    color="grey lighten-4"
  >
    <div style="font-size: 16px; font-weight: 900; margin-bottom: 20px">
      Sidebar TOC here
    </div>
    <div
      v-if="els && els.length"
      style="padding-left: 15px; padding-right: 5px"
    >
      <div v-for="(item, index) in els" :key="index">
        <span class="hover" @click="gotoHeading(item)">{{
          item.innerHTML
        }}</span>
      </div>
    </div>
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
    els: null,
  }),
  async created() {},
  async mounted() {
    await this.$nextTick(() => {
      const nodes = document.querySelectorAll('h2')
      this.els = [...nodes]
      console.log('sidebar els: ', this.els)
    })

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
    gotoHeading(item) {
      console.log('item: ', item.id)
      this.drawer = false
      this.$vuetify.goTo(`#${item.id}`, { offset: 8 })
    },
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
