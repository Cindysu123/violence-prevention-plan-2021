<template>
  <v-dialog v-model="dialog" width="600px">
    <v-card>
      <div v-if="!loading">
        <div
          style="
            font-size: 18px;
            text-transform: uppercase;
            color: #fff;
            font-weight: bold;
            background: #aaa;
          "
          class="px-3 py-2"
        >
          {{ meta.title }}
        </div>
        <div style="font-size: 18px; font-weight: 900" class="px-3 py-2">
          {{ meta.heading }}
        </div>

        <v-card-text>
          <nuxt-content
            :document="markdown"
            class="markdown-body"
          ></nuxt-content
        ></v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn color="green darken-1" text @click="dialog = false">
            Close
          </v-btn>
        </v-card-actions>
      </div>
      <div v-else>
        <Loader></Loader>
      </div>
    </v-card>
  </v-dialog>
</template>

<script>
import { EventBus } from '@/event-bus'
export default {
  data() {
    return {
      dialog: false,
      markdown: null,
      meta: null,
      loading: true,
    }
  },
  mounted() {
    EventBus.$on('showGoal', (goal) => {
      // eslint-disable-next-line no-console
      // console.log('goal: ', goal)
      this.meta = goal
      this.dialog = true
      this.fetchContent(goal)
    })
  },
  methods: {
    async fetchContent(goal) {
      this.loading = true
      this.markdown = await this.$content(`goals/${goal.markdown}`).fetch()
      // eslint-disable-next-line no-console
      // console.log(markdown)

      this.loading = false
    },
  },
}
</script>

<style lang="scss" scoped></style>
