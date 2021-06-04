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
    <div v-if="orientation === 'inline-left'">
      <div
        style="
          float: left;
          padding-right: 15px;
          padding-top: 15px;
          padding-bottom: 5px;
        "
      >
        <v-img
          :src="`https://dummyimage.com/${width}x${height}`"
          :alt="alt"
          :height="height"
          :width="width"
        ></v-img>
      </div>
    </div>
    <div v-if="orientation === 'inline-right'">
      <div
        style="
          float: right;
          padding-left: 15px;
          padding-top: 15px;
          padding-bottom: 5px;
        "
      >
        <v-img
          :src="`https://dummyimage.com/${width}x${height}`"
          :alt="alt"
          :height="height"
          :width="width"
        ></v-img>
      </div>
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
      default: '200',
    },
    height: {
      type: String,
      default: '200',
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
      default: '',
    },
  },
}
</script>

<style></style>
