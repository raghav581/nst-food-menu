<template>
  <q-page class="q-pa-md">
    <q-markup-table>
      <thead>
        <tr>
          <th>Day</th>
          <th>Monday</th>
          <th>Tuesday</th>
          <th>Wednesday</th>
          <th>Thursday</th>
          <th>Friday</th>
          <th>Saturday</th>
          <th>Sunday</th>
        </tr>
      </thead>
    </q-markup-table>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage',

  setup() {
    const currentMenu = {}

    return {
      currentMenu,
    }
  },
})
</script>
