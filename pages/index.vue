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
      loading: true,
    }
  },
  watch: {
    loading(newValue) {
      console.log('loading: ', newValue)
    },
  },
  async mounted() {
    await this.$nextTick(() => {
      console.log('loading: ', this.loading)
      console.log('content ready')
      this.fixA11y()
      const vm = this
      const fnRef = document.getElementsByClassName('footnote-ref')
      for (let i = 0; i < fnRef.length; i++) {
        fnRef[i].addEventListener(
          'click',
          function (e) {
            e.preventDefault()
            // console.log(this.getAttribute('href'))
            vm.$vuetify.goTo(this.getAttribute('href'), { offset: 100 })
          },
          10
        )
      }
      const elements = document.getElementsByClassName('footnote-backref')
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
      this.loading = false
    })
  },
  beforeDestroy() {
    window.removeEventListener('click', null)
    console.log('beforeDestroy')
  },
  methods: {
    fixA11y() {
      console.log('a11y fixes here')
    },
  },
}
</script>
