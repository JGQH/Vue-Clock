<template>
  <div :class='["tile", state ? "neu-in" : "neu-out"]'></div>
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
  border-radius: .5rem;
}

.neu-in, .neu-out {
  --color-light: hsl(0, 0%, 20%);
  --color-base: hsl(0, 0%, 15%);
  --color-dark: hsl(0, 0%, 10%);

  background: var(--color-base);
}

.neu-in {
  box-shadow: -.5rem -.5rem .5rem var(--color-light),
              .5rem .5rem .5rem var(--color-dark)
}

.neu-out {
  box-shadow: inset -.5rem -.5rem .5rem var(--color-light),
              inset .5rem .5rem .5rem var(--color-dark)
}
</style>