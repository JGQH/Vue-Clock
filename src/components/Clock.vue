<template>
  <div class='clock-container'>
    <Block :value="hours" />
    <Block :value="minutes" />
    <Block :value="seconds" />
  </div>
</template>

<script lang='ts'>
import { defineComponent } from 'vue'
import Block from './Block.vue'

export default defineComponent({
  name: 'Clock',
  components: {
    Block
  },
  data() {
    const time = new Date()

    return {
      hours: time.getHours(),
      minutes: time.getMinutes(),
      seconds: time.getSeconds()
    }
  }
})
</script>

<style scoped>
.clock-container {
  align-self: center;
  justify-self: center;

  width: 60vw;
  height: 100vh;

  padding: 1rem;
  column-gap: 1rem;

  display: flex;
  flex-direction: row;
  justify-content:space-between;
}
</style>