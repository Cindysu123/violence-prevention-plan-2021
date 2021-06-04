<template>
  <div>
    <div v-if="orientation === 'center'" class="text-center image">
      <v-container fluid>
        <v-layout justify-center align-center>
          <v-flex shrink>
            <v-img
              :src="`https://dummyimage.com/${width}x${height}`"
              :alt="alt"
            ></v-img>
          </v-flex>
        </v-layout>
        <v-layout justify-center align-center>
          <v-flex shrink>
            <div class="image--caption">{{ caption }}</div></v-flex
          >
        </v-layout>
      </v-container>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      default: '',
    },
    width: {
      type: String,
      default: '1000',
    },
    height: {
      type: String,
      default: '400',
    },

    orientation: {
      type: String,
      default: 'center',
    },
    alt: {
      type: String,
      default: 'This is the default alt text',
    },
    caption: {
      type: String,
      default: 'This is the default caption',
    },
  },
}
</script>

<style>
.image {
  margin-top: 30px;
  margin-bottom: 30px;
}

.image--caption {
  font-size: 14px;
  color: #555;
}
</style>
