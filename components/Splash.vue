<template>
  <!-- <v-img :src="`/${image}`" :height="height" :alt="alt"></v-img> -->
  <v-img
    src="https://dummyimage.com/16:9x1080&text=Splash image here"
    :height="height"
    :alt="alt"
  ></v-img>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      default: '',
      required: true,
    },
    height: {
      type: String,
      default: '400px',
    },
    alt: {
      type: String,
      default: 'This is the default alt text',
    },
  },
}
</script>

<style lang="scss" scoped></style>
