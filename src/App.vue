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

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;

  display: grid;
}
</style>
