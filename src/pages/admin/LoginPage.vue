<template>
  <q-page class="flex flex-center">
    <q-card>
      <q-card-section>
        <q-input outlined type="password" label="Admin Password" v-model="adminPassword">
          <template v-slot:prepend>
            <q-icon name="lock" />
          </template>
        </q-input>
      </q-card-section>
      <q-separator></q-separator>
      <q-card-section>
        <q-btn push label="Login" color="primary" @click="login" class="full-width" />
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'
import { api } from 'src/boot/axios'
import { useQuasar } from 'quasar'
import { useRouter } from 'vue-router'

const adminPassword = ref('')

const $q = useQuasar()
const router = useRouter()

function login() {
  $q.loading.show()
  api
    .post('/admin/login', { password: adminPassword.value })
    .then(() => {
      $q.notify({ type: 'positive', message: 'Login successful!' })
      router.push('/admin')
    })
    .catch(() => {
      $q.notify({ type: 'negative', message: 'Login failed. Please check your password.' })
    })
    .finally(() => {
      $q.loading.hide()
    })
}
</script>
