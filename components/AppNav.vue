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
      style
      @click="
        $router.push('/').catch((err) => {
          $vuetify.goTo(0)
        })
      "
    />

    <div
      style="font-size: 24px; font-weight: bold; margin-left: 5px"
      class="hover hidden-sm-and-down"
      @click="
        $router.push('/').catch((err) => {
          $vuetify.goTo(0)
        })
      "
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
  },
}
</script>

<style lang="scss" scoped></style>
