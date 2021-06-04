<template>
  <div>
    <nuxt-content :document="page" class="markdown-body" />
  </div>
</template>

<script>
/* eslint-disable no-console */
export default {
  async asyncData({ $content }) {
    const page = await $content('index').fetch()
    return {
      page,
    }
  },
  async mounted() {
    await this.$nextTick(() => {
      console.log('mounted')
    })
  },
}
</script>
