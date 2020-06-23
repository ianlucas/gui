<template>
  <button
    v-bind="$attrs"
    v-on="$listeners"
    class="gui-button"
  >
    <slot />
  </button>
</template>

<style>
.gui-button {
  border: none;
  background-color: transparent;
  box-shadow: 0 0 0 1px transparent inset;
  min-width: 81px;
  padding: 3px 0;
  text-align: center;
  transition: all ease 300ms;
}

.gui-button:focus {
  border-color: #2a73b9;
  box-shadow: 0 0 0 1px #cce4f7 inset;
  position: relative;
  transition: none;
  outline: none;
}

.gui-button:hover {
  border-color: #2a73b9;
  background-color: #e5f1fB;
  box-shadow: none;
}

.gui-button:active {
  background-color: #cce4f7;
}

.gui-button:disabled {
  border-color: #bebebe;
  background-color: #cdcdcd;
}
</style>
