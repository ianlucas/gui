<template>
  <div :class="{
    'gui-panel': true,
    'isScrollable': scrollable
  }">
    <slot />
  </div>
</template>

<style>
.gui-panel.isScrollable {
  overflow-y: scroll;
  overflow-x: hidden;
}

.gui-panel.isScrollable::-webkit-scrollbar {
  background-color: #f1f1f1;
  width: 12px;
}

.gui-panel.isScrollable::-webkit-scrollbar-thumb {
  background-color: #a1a1a1;
}
</style>

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
    },

    scrollable: {
      type: Boolean,
      default: false
    }
  }
}
</script>
