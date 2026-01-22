<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title> NST Food Menu </q-toolbar-title>

        <q-btn flat label="Admin" icon="settings" aria-label="Admin" to="/admin" />
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'MainLayout',

  setup() {
    return {}
  },
})
</script>
