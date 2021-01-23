<template>
  <div class="col-12">
    <div class="row q-col-gutter-md">

      <div class="col-12">
        <div class="row items-center q-gutter-sm">
          <div class="text-h4 text-white">{{ label }}</div>
          <q-space/>
          <div class="text-white q-px-md text-h6 text-weight-light">
            <span v-if="hasThermostat">
              <q-icon name="svguse:ios/thermometer.svg#main" size="1.3em"/>
              {{ deviceAvgTemperature }}/{{ groupAvgTemperature }} &deg;C
            </span>
            <span v-if="hasConsumption">
              <q-icon name="svguse:ios/bolt.svg#main" size="1.3em"/>
              {{ deviceSumConsumption }} W
            </span>
          </div>
          <q-btn-group rounded unelevated v-if="hasLights">
            <q-btn rounded color="trans-1" size="lg" icon="svguse:ios/light.svg#on"/>
            <q-btn rounded color="trans-1" size="lg" icon="svguse:ios/light.svg#turn-off"/>
          </q-btn-group>
          <q-btn-group rounded unelevated v-if="hasShutters">
            <q-btn rounded color="trans-1" size="lg" icon="svguse:ios/shutter.svg#up"/>
            <q-btn rounded color="trans-1" size="lg" icon="svguse:ios/shutter.svg#down"/>
            <q-btn rounded color="trans-1" size="lg" icon="svguse:ios/shutter.svg#pause"/>
          </q-btn-group>
        </div>
        <q-separator class="q-mt-md"/>
      </div>

      <device-button type="light" label="Corredor"/>
      <device-button type="shutter" label="Janela"/>

    </div>
  </div>
</template>

<script lang="ts">
import {defineComponent} from '@vue/composition-api';
import DeviceButton from "components/DeviceButton.vue";

export default defineComponent({
  name: 'Group',
  components: {DeviceButton},
  props: {
    label: String,
    devices: Array
  },
  computed: {
    hasThermostat() {
      // TODO: check in devices list
      return true;
    },
    hasConsumption() {
      // TODO: check in devices list
      return true;
    },
    hasLights() {
      // TODO: check in devices list
      return true;
    },
    hasShutters() {
      // TODO: check in devices list
      return true;
    },
    deviceAvgTemperature() {
      // TODO: check in devices list
      return 15;
    },
    groupAvgTemperature() {
      // TODO: check in devices list
      return 12;
    },
    deviceSumConsumption() {
      // TODO: check in devices list
      return 42;
    }
  }
});
</script>
