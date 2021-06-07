<template>
  <div class="my-12">
    <component :is="name"></component>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      default: '',
    },
  },
}
</script>

<style lang="scss" scoped></style>
