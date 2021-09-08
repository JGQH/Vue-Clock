<template>
  <div class='tile'>{{ state }}</div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Tile',
  props: {
    state: {
      type: Boolean,
      required: true
    }
  }
})
</script>

<style scoped>
.tile {
  width: 100%;
  aspect-ratio: 1;
}
</style>