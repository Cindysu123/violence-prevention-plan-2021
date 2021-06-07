<template>
  <v-app-bar app color="white" height="90" fixed scroll-threshold="1" style="">
    <v-spacer
      v-if="$vuetify.breakpoint.sm || $vuetify.breakpoint.xs"
    ></v-spacer>

    <v-img
      alt="ICJIA Logo"
      class="shrink ml-0 mr-2 hover appBar"
      contain
      src="/icjia-logo.png"
      transition="scale-transition"
      width="90"
      @click="gotoTop()"
    />

    <div
      style="
        font-size: 24px;
        font-weight: bold;
        margin-left: 5px;
        text-transform: uppercase;
      "
      class="hover hidden-sm-and-down"
      @click="gotoTop()"
    >
      Statewide Violence Prevention Plan: 2020-2024
    </div>

    <v-spacer></v-spacer>
    <v-tooltip bottom>
      <template #activator="{ on, attrs }">
        <v-btn
          small
          v-bind="attrs"
          class="mr-5"
          v-on="on"
          @click="downloadReport()"
          >Full <span class="hidden-sm-and-down">Report</span
          ><v-icon right>mdi mdi-file-pdf-outline</v-icon></v-btn
        >
      </template>
      <span>Download full report</span>
    </v-tooltip>
    <v-tooltip bottom>
      <template #activator="{ on, attrs }">
        <v-btn
          text
          style="font-weight: bold"
          v-bind="attrs"
          v-on="on"
          @click="toggleSidebar"
        >
          <v-icon>mdi mdi-menu</v-icon></v-btn
        >
      </template>
      <span>Open table of contents</span>
    </v-tooltip>

    <!-- <v-app-bar-nav-icon
      aria-label="Click to toggle sidebar"
      @click="toggleSidebar"
    ></v-app-bar-nav-icon> -->
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
    downloadReport() {
      // eslint-disable-next-line no-console
      console.log('download report here')
    },
  },
}
</script>

<style>
.appBar {
  border-bottom: 1px solid #eee !important;
}
</style>
