<template>
  <v-app-bar app title style="-webkit-app-region: drag; -webkit-user-select: none;">
    <v-btn icon style="-webkit-app-region: no-drag;" @click="min">
      <v-icon>arrow_back</v-icon>
    </v-btn>
    <v-btn icon style="-webkit-app-region: no-drag;" @click="max">
      <v-icon>arrow_forward</v-icon>
    </v-btn>
    <v-btn icon style="-webkit-app-region: no-drag;" @click="close">
      <v-icon>refresh</v-icon>
    </v-btn>
    <v-toolbar-title>
      {{ title }}
    </v-toolbar-title>
    <v-spacer></v-spacer>
    <v-btn icon style="-webkit-app-region: no-drag;" @click="min">
      <v-icon>mdi-minus</v-icon>
    </v-btn>
    <v-btn icon style="-webkit-app-region: no-drag;" @click="max">
      <v-icon>{{ isMax ? 'fullscreen_exit' : 'fullscreen' }}</v-icon>
    </v-btn>
    <v-btn icon style="-webkit-app-region: no-drag;" @click="close">
      <v-icon>mdi-close</v-icon>
    </v-btn>
  </v-app-bar>
</template>

<script>
import { minWindow, maxWindow, close, isMaxWindow } from '@/utils/renderer'
export default {
  data() {
    return {
      isMax: false
    }
  },
  mounted() {
    this.isMaxWindow()
  },
  methods: {
    min() {
      minWindow()
    },
    max() {
      maxWindow()
    },
    close() {
      close()
    },
    isMaxWindow() {
      this.isMax = isMaxWindow()
    }
  }
}
</script>
