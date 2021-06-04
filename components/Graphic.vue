<template>
  <div>
    <div v-if="orientation === 'center'" class="text-center image">
      <v-container fluid>
        <v-layout justify-center align-center>
          <v-flex shrink>
            <v-img
              :src="`https://dummyimage.com/${width}x${height}`"
              :lazy-src="`https://dummyimage.com/10x10`"
              :alt="alt"
            >
              <template #placeholder>
                <v-row class="fill-height ma-0" align="center" justify="center">
                  <v-progress-circular
                    indeterminate
                    color="grey lighten-5"
                  ></v-progress-circular>
                </v-row> </template
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
          :lazy-src="`https://dummyimage.com/10x10`"
          :alt="alt"
          :height="height"
          :width="width"
        >
          <template #placeholder>
            <v-row class="fill-height ma-0" align="center" justify="center">
              <v-progress-circular
                indeterminate
                color="grey lighten-5"
              ></v-progress-circular>
            </v-row> </template
        ></v-img>
        <div class="text-center image--caption">{{ caption }}</div>
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
          :lazy-src="`https://dummyimage.com/10x10`"
          :alt="alt"
          :height="height"
          :width="width"
        >
          <template #placeholder>
            <v-row class="fill-height ma-0" align="center" justify="center">
              <v-progress-circular
                indeterminate
                color="grey lighten-5"
              ></v-progress-circular>
            </v-row> </template
        ></v-img>
        <div class="text-center image--caption">{{ caption }}</div>
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
      type: Number,
      default: 200,
    },
    height: {
      type: Number,
      default: 200,
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
