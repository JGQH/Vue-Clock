<template>
  <Clock />
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Clock from './components/Clock.vue'

export default defineComponent({
  name: 'App',
  components: {
    Clock
  }
});
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  background: radial-gradient(circle, hsl(0,0%,16%) 0%, hsl(0,0%,14%))
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  display: grid;
}
</style>
