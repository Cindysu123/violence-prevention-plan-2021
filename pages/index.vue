<template>
  <client-only>
    <div style="" class="pb-12">
      <nuxt-content :document="page" class="markdown-body pageTopBuffer" />
    </div>
  </client-only>
</template>

<script>
/* eslint-disable no-console */
/* eslint-disable no-unused-vars */
import { EventBus } from '@/event-bus'

import { fixNuxtContentHeadings, fixBlankTableHeadings } from '@/a11y'

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
            vm.$vuetify.goTo(this.getAttribute('href'), { offset: 200 })
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
    // remove all eventListeners
    const backrefEls = document.getElementsByClassName('footnote-backref')
    const backrefElsClone = backrefEls.cloneNode(true)
    backrefEls.parentNode.replaceChild(backrefElsClone, backrefEls)

    const footnoterefEls = document.getElementsByClassName('footnote-ref')
    const footnoterefElsClone = footnoterefEls.cloneNode(true)
    footnoterefEls.parentNode.replaceChild(footnoterefElsClone, footnoterefEls)

    console.log('beforeDestroy: removeEventListeners')
  },
  methods: {
    fixA11y() {
      fixNuxtContentHeadings()

      fixBlankTableHeadings()
      window.jQuery('.footnote-backref').each(function (index) {
        window.jQuery(this).text('^')
      })

      window
        .jQuery('<h2 id="references">References</h2>')
        .insertAfter('.footnotes hr')
      console.log('a11y fixes applied')
    },
  },
}
</script>

<style>
.pageTopBuffer {
  margin-top: 90px;
}

#references {
  margin-left: 15px;
  margin-right: 15px;
}
</style>
