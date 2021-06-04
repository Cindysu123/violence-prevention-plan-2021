<template>
  <!-- <v-img :src="`/${image}`" :height="height" :alt="alt"></v-img> -->
  <v-img
    :src="`https://dummyimage.com/16:9x1080&text=${temp}`"
    :lazy-src="`https://dummyimage.com/10x10&text=${temp}`"
    :height="height"
    :alt="alt"
    class="splash"
  >
    <template #placeholder>
      <v-row class="fill-height ma-0" align="center" justify="center">
        <v-progress-circular
          indeterminate
          color="grey lighten-5"
        ></v-progress-circular>
      </v-row>
    </template>
  </v-img>
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
      type: Number,
      default: 500,
    },
    temp: {
      type: String,
      default: 'This is the placeholder text',
    },
    alt: {
      type: String,
      default: 'This is the default alt text',
    },
  },
}
</script>

<style lang="scss" scoped></style>
