<template>
  <div class="col-lg-1 col-md-3 col-sm-4 col-xs-6 overflow-hidden">
    <q-card class="cursor-pointer bg-trans-1 non-selectable full-width"
            v-ripple.early.center dark flat
            @click="handleClick">
      <div class="q-px-md q-pt-sm">
        <div class="row justify-center">
          <component :is="type" :active="active"/>
        </div>
      </div>
      <q-card-section horizontal>
        <div class="text-weight-light text-center q-pb-md q-pt-sm q-px-md full-width">
          {{ label }}
        </div>
      </q-card-section>
    </q-card>
  </div>
</template>

<script lang="ts">
import {defineComponent, ref} from '@vue/composition-api';
import Light from "components/Light.vue";
import Shutter from "components/Shutter.vue";

export default defineComponent({
  name: 'DeviceButton',
  components: {Shutter, Light},
  props: {
    type: {
      type: String,
      required: true
    },
    label: {
      type: String,
      required: true
    }
  },
  setup() {
    const active = ref(false);
    return {active};
  },
  methods: {
    handleClick() {
      this.active = !this.active
    }
  }
});
</script>
