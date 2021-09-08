<template>
  <Tileset class="block" :value="leftVal" />
  <Tileset class="block" :value="rightVal" />
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Tileset from './Tileset.vue'

export default defineComponent({
  name: 'Block',
  props: {
    value: {
      type: Number,
      required: true
    }
  },
  components: {
    Tileset
  },
  computed: {
    leftVal() {
      return Math.floor(this.value / 10)
    },
    rightVal() {
      return this.value % 10
    }
  }
})
</script>

<style scoped>
.block {
  flex: 0 1 calc(100% / 6);
}
</style>