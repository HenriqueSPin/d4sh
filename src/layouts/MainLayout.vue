<template>
  <q-layout view="hHh lpR fFf">
    <q-header class="bg-transparent">
      <q-toolbar>
        <q-toolbar-title>
          D4SH
        </q-toolbar-title>

        <q-btn
          flat
          dense
          round
          icon="las la-bars"
          aria-label="Menu"
          @click="rightDrawerOpen = !rightDrawerOpen"
        />
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="rightDrawerOpen"
      side="right" overlay elevated
    >
      Quasar v{{ $q.version }}
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">

import { defineComponent, ref } from '@vue/composition-api';

export default defineComponent({
  name: 'MainLayout',
  setup() {
    const rightDrawerOpen = ref(false);

    return {rightDrawerOpen}
  }
});
</script>
