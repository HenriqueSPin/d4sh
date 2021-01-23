<template>
  <base-icon :icon="icon"
             :text-color="active ? 'yellow-9' : ''"
             :active="active"/>
</template>

<script lang="ts">
import {defineComponent} from '@vue/composition-api';
import BaseIcon from "components/BaseIcon.vue";

export default defineComponent({
  name: 'Light',
  components: {BaseIcon},
  props: {
    active: Boolean
  },
  computed: {
    icon() {
      let id = this.active ? 'on' : 'off'
      return 'svguse:ios/light.svg#' + id
    }
  }
});
</script>
