<template>
  <div class="gui-toolbar">
    <slot />
  </div>
</template>

<style>
.gui-toolbar {
  padding: 1em;
}

.gui-toolbar .gui-select {
  border: none;
  text-align: center;
  text-align-last: center;
  width: 100%;
}

.gui-toolbar > .gui-select,
.gui-toolbar > .gui-button {
  margin-right: 0.5em;
}
</style>
