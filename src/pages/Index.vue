<template>
  <q-page class="row items-center justify-evenly">

    <div class="q-layout-padding full-width">
      <div class="row q-col-gutter-md">

        <group label="Sala"></group>

      </div>
    </div>

  </q-page>
</template>

<script lang="ts">
import {Todo, Meta} from 'components/models';
import {defineComponent, ref} from '@vue/composition-api';
import Group from "components/Group.vue";

export default defineComponent({
  name: 'PageIndex',
  components: {Group},
  setup() {
    const todos = ref<Todo[]>([
      {
        id: 1,
        content: 'ct1'
      },
      {
        id: 2,
        content: 'ct2'
      }
    ]);
    const meta = ref<Meta>({
      totalCount: 1200
    });
    const on = ref(false);
    return {todos, meta, on};
  }
});
</script>
