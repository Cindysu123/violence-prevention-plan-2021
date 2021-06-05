<template>
  <div style="margin-top: 90px">
    <nuxt-content :document="page" class="markdown-body" />
  </div>
</template>

<script>
/* eslint-disable no-console */
/* eslint-disable no-unused-vars */
import { EventBus } from '@/event-bus'
// import { fixNuxtContentHeadings } from '@/a11y'

export default {
  async asyncData({ $content }) {
    const page = await $content('index').fetch()
    return {
      page,
    }
  },
  data() {
    return {
      elArr: () => [],
    }
  },
  async mounted() {
    await this.$nextTick(() => {
      console.log('content ready')
      this.fixA11y()
      const elements = document.getElementsByClassName('footnote-backref')
      const vm = this
      for (let i = 0; i < elements.length; i++) {
        elements[i].addEventListener(
          'click',
          function (e) {
            e.preventDefault()
            vm.$vuetify.goTo(this.getAttribute('href'), { offset: 15 })
          },
          10
        )
      }
    })
  },
  methods: {
    fixA11y() {
      console.log('a11y fixes here')
    },
  },
}
</script>
