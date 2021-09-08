<template>
  <div class="tileset">
    <Tile :state="states[0]" />
    <Tile :state="states[1]" />
    <Tile :state="states[2]" />
    <Tile :state="states[3]" />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Tile from './Tile.vue'

export default defineComponent({
  name: 'Tileset',
  props: {
    value: {
      type: Number,
      required: true
    }
  },
  components: {
    Tile
  },
  computed: {
    states() {
      const binary = this.value.toString(2).padStart(4, '0').split('')
      return binary.map(val => val === '1')
    }
  }
})
</script>

<style scoped>
.tileset {
  display: flex;
  flex-direction: column;
  justify-content: center;

  row-gap: 1rem;
}
</style>
