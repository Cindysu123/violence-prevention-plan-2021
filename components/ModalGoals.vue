<template>
  <v-dialog v-model="dialog" width="600px">
    <v-card>
      <div v-if="!loading">
        <v-card-title>
          <span>{{ meta.title }}</span>
        </v-card-title>
        <v-card-text>{{ meta.heading }}</v-card-text>
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
