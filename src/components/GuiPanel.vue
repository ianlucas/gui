<template>
  <div class="gui-panel">
    <slot />
  </div>
</template>

<script>
export default {
  props: {
    size: {
      type: Number,
      default: 0
    },

    minSize: {
      type: Number,
      default: 0
    }
  }
}
</script>
