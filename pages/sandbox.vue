<template>
  <div style="margin-top: 90px">
    <v-timeline>
      <v-timeline-item
        v-for="(goal, i) in goals"
        :key="i"
        color="grey darken-2"
        fill-dot
      >
        <!-- <template #opposite>
          <span
            :class="`headline font-weight-bold ${goal.color}--text`"
            style="text-transform: uppercase"
            v-text="goal.title"
          ></span>
        </template> -->

        <v-card class="pb-4">
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
            {{ goal.title }}
          </div>
          <div style="font-size: 18px; font-weight: 900" class="px-3 py-2">
            {{ goal.heading }}
          </div>

          <v-card-actions class="px-4">
            <v-spacer></v-spacer>
            <v-btn small color="grey darken-2" dark @click="showGoal(goal)">
              Details
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-timeline-item>
    </v-timeline>
  </div>
</template>

<script>
import { EventBus } from '@/event-bus'
export default {
  data: () => ({
    goals: [
      {
        color: 'grey',
        title: 'Goal #1',
        heading: 'Stop Violence and Promote Safety.',
        markdown: 'goal01',
      },
      {
        color: 'grey',
        title: 'Goal #2',
        heading:
          'Support Children, Youth, and Families by Emphasizing Programs that Foster Social Connectedness and Belonging.',
        markdown: 'goal02',
      },
      {
        color: 'grey',
        title: 'Goal #3',
        heading:
          'The ability to live without fear of harm is a fundamental human right and essential to individual, family, and community development and success.',
        markdown: 'goal03',
      },
      {
        color: 'grey',
        title: 'Goal #4',
        heading:
          'The ability to live without fear of harm is a fundamental human right and essential to individual, family, and community development and success.',
        markdown: 'goal04',
      },
      {
        color: 'grey',
        title: 'Goal #5',
        heading:
          'The ability to live without fear of harm is a fundamental human right and essential to individual, family, and community development and success.',
        markdown: 'goal05',
      },
    ],
  }),
  methods: {
    showGoal(goal) {
      EventBus.$emit('showGoal', goal)
    },
  },
}
</script>
