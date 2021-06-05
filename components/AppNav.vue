<template>
  <v-app-bar
    app
    color="white"
    height="90"
    fixed
    scroll-threshold="1"
    style="border-bottom: 1px solid #eee !important"
  >
    <v-app-bar-nav-icon @click="toggleSidebar"></v-app-bar-nav-icon>

    <v-spacer
      v-if="$vuetify.breakpoint.sm || $vuetify.breakpoint.xs"
    ></v-spacer>

    <v-img
      alt="ICJIA Logo"
      class="shrink ml-2 mr-2 hover"
      contain
      src="/icjia-logo.png"
      transition="scale-transition"
      width="90"
      @click="gotoTop()"
    />

    <div
      style="font-size: 24px; font-weight: bold; margin-left: 5px"
      class="hover hidden-sm-and-down"
      @click="gotoTop()"
    >
      VIOLENCE PREVENTION PROJECT
    </div>

    <v-spacer></v-spacer>
  </v-app-bar>
</template>

<script>
import { EventBus } from '@/event-bus'
export default {
  props: {
    toc: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    toggleSidebar() {
      EventBus.$emit('toggleSidebar')
    },
    gotoTop() {
      // eslint-disable-next-line no-console
      // console.log('goto Top')
      this.$vuetify.goTo(0)
    },
  },
}
</script>

<style lang="scss" scoped></style>
