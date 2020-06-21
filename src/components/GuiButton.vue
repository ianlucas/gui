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
  box-shadow: 0 0 0 1px #2a73b9 inset;
  position: relative;
  transition: none;
  outline: none;
}

.gui-button:focus:after {
  border: 1px dotted #333;
  content: '';
  display: block;
  height: calc(100% - 4px);
  left: 1px;
  position: absolute;
  top: 1px;
  width: calc(100% - 4px);
}

.gui-button:hover {
  border-color: #2a73b9;
  background-color: #e5f1fB;
  box-shadow: none;
}

.gui-button:disabled {
  border-color: #bebebe;
  background-color: #cdcdcd;
}
</style>
