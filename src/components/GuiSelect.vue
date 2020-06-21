<template>
  <span class="gui-select">
    <GuiButton
      class="gui-select-button"
      @blur="handleBlur"
      @click="toggleVisibility"
    >
      {{ innerValue || placeholder }}
      <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 292.362 292.362"
      >
        <path d="M286.935 69.377c-3.614-3.617-7.898-5.424-12.848-5.424H18.274c-4.952 0-9.233 1.807-12.85 5.424C1.807 72.998 0 77.279 0 82.228c0 4.948 1.807 9.229 5.424 12.847l127.907 127.907c3.621 3.617 7.902 5.428 12.85 5.428s9.233-1.811 12.847-5.428L286.935 95.074c3.613-3.617 5.427-7.898 5.427-12.847 0-4.948-1.814-9.229-5.427-12.85z" />
      </svg>
    </GuiButton>
    <ul
      v-show="isVisible"
      class="gui-select-select"
    >
      <li
        v-if="placeholder"
        class="gui-select-option"
      >
        <GuiButton :disabled="true">{{ placeholder }}</GuiButton>
      </li>
      <li
        v-for="option of options"
        :key="option.value"
        class="gui-select-option"
        @click="handleInput(option)"
        @mouseenter="setInside(true)"
        @mouseleave="setInside(false)"
      >
        <GuiButton>{{ option.label }}</GuiButton>
      </li>
    </ul>
  </span>
</template>

<style>
.gui-select {
  position: relative;
}

.gui-select-button {
  text-align: left;
  min-width: auto;
  padding-left: 0.5em;
  padding-right: 0.5em;
  width: auto;
}

.gui-select-button svg {
  height: 8px;
  margin-left: 3px;
  vertical-align: middle;
  width: 8px;
}

.gui-select-select {
  border: 1px solid #f1f1f1;
  background-color: #fff;
  box-shadow: 2px 2px 2px rgba(0, 0, 0, 0.1);
  list-style: none;
  left: 1em;
  margin: 0;
  padding: 0;
  position: absolute;
  top: 1em;
  z-index: 1;
}

.gui-select-option .gui-button {
  text-align: left;
  text-align-last: left;
  padding: 3px 0.5em;
  width: 100%;
}

.gui-select-option .gui-button:disabled {
  background-color: transparent;
}

.gui-select-option .UiBar-space {
  margin: 0;
}
</style>

<script>
import GuiButton from '@/components/GuiButton.vue'

export default {
  components: {
    GuiButton
  },

  props: {
    placeholder: {
      type: String,
      default: ''
    },

    options: {
      type: Array,
      default: () => ([])
    },

    value: {
      type: String,
      default: ''
    }
  },

  data: () => ({
    innerValue: null,
    isVisible: false,
    isInside: false
  }),

  methods: {
    handleInput (option) {
      this.innerValue = option.label
      this.$emit('input', option.value)
      this.setVisibility(false)
    },

    handleBlur (e) {
      if (this.isInside) {
        return
      }
      this.isVisible = false
    },

    toggleVisibility () {
      this.isVisible = !this.isVisible
    },

    setVisibility (value) {
      this.isVisible = value
    },

    setInside (value) {
      this.isInside = value
    }
  }
}
</script>
