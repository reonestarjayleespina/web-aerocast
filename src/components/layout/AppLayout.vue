<!-- <script setup>
 import { ref } from 'vue'

const theme = ref('light')

function onClick () {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script> -->

<template>
  <v-responsive class="border rounded">
    <v-app>
      <!-- <v-app-bar class="px-3">
        <v-spacer></v-spacer>

        <v-btn :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'" text="Toggle Theme" slim
          @click="onClick"></v-btn>
      </v-app-bar> -->

      <v-main>
        <v-container class="full-height mt-16" fluid>
            <slot name="login_reg"></slot>
        </v-container>
      </v-main>

      <v-footer border app>2024 - AeroCast</v-footer>
    </v-app>
  </v-responsive>
</template>