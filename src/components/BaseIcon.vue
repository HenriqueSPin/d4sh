<template>
  <q-avatar size="60px" font-size="50px"
            :text-color="textColor || (active ? 'white' : 'trans-2')"
            :icon="icon"/>
</template>

<script lang="ts">
import {defineComponent} from '@vue/composition-api';

export default defineComponent({
  name: 'BaseIcon',
  props: {
    icon: {
      type: String,
      required: true
    },
    active: Boolean,
    textColor: String
  }
});
</script>
