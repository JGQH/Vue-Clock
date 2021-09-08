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
      interval: 0,
      hours: time.getHours(),
      minutes: time.getMinutes(),
      seconds: time.getSeconds()
    }
  },
  beforeUnmount() {
    clearInterval(this.interval)
  },
  beforeMount() {
    this.interval = setInterval(this.update, 1000)
  },
  methods: {
    update() {
      const time = new Date()

      this.hours = time.getHours()
      this.minutes = time.getMinutes()
      this.seconds = time.getSeconds()
    }
  }
})
</script>

<style scoped>
.clock-container {
  align-self: center;
  justify-self: center;

  width: 100vw;
  height: 100vh;

  padding: 1rem;
  column-gap: 1rem;

  display: flex;
  flex-direction: row;
  justify-content:space-between;
}

@media screen and (orientation:landscape) {
  .clock-container {
    width: 60vw;
  }
}
</style>