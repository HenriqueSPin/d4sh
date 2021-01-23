<template>
  <base-icon :icon="icon"
             :active="active"/>
</template>

<script lang="ts">
import {defineComponent} from '@vue/composition-api';
import BaseIcon from "components/BaseIcon.vue";

export default defineComponent({
  name: 'Shutter',
  components: {BaseIcon},
  setup() {
    const step = 0
    const direction = 'up'
    const timer = null

    return {step, direction, timer}
  },
  props: {
    active: Boolean
  },
  computed: {
    icon () {
      const ids = {
        0: 'closed',
        1: 'half',
        2: 'open',
      }
      let id = this.active ? ids[this.step] : 'closed'
      return 'svguse:ios/shutter.svg#' + id
    }
  },
  mounted() {
    this.setTimer()
  },
  methods: {
    up() {
      this.direction = 'up'
      this.setTimer()
    },

    down() {
      this.direction = 'down'
      this.setTimer()
    },

    setTimer() {
      this.cleatTimer()
      this.timer = setInterval(this.move, 300)
    },

    cleatTimer() {
      clearInterval(this.timer)
    },

    move() {
      this.step += this.direction === 'up' ? 1 : -1
      if (this.step < 0) {
        this.step = 2
      }
      if (this.step > 2) {
        this.step = 0
      }
    }
  }
});
</script>
