<template>
  <div
    class="gui-split"
    :style="{
      height: size
    }"
  >
    <slot />
  </div>
</template>

<style>
.gui-split {
  width: 100%;
}
.gutter.gutter-vertical {
  cursor: ns-resize !important;
  position: relative;
}
.gutter.gutter-vertical:after {
  content: '';
  display: block;
  height: 8px;
  width: 100%;
  position: absolute;
  top: -3px;
  z-index: 10;
}
</style>

<script>
import Split from 'split.js'

export default {
  props: {
    size: {
      type: String,
      default: '100%'
    },
    gutterSize: {
      type: Number,
      default: 1
    }
  },

  mounted () {
    const elements = []
    const sizes = []
    const minSizes = []

    this.$children.map(child => {
      elements.push(child.$el)
      sizes.push(child.$props.size)
      minSizes.push(child.$props.minSize)
    })

    Split(elements, {
      sizes,
      minSizes,
      direction: 'vertical',
      gutterSize: this.gutterSize,
      onDrag: () => {
        this.$emit('drag')
      }
    })
  }
}
</script>
