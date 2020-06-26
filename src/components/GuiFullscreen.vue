<template>
  <div class="gui-viewport">
    <slot />
  </div>
</template>

<style>
* {
  box-sizing: border-box;
}

*::-webkit-scrollbar {
  background-color: #fff;
  height: 14px;
  transition: 500ms ease all;
  width: 14px;
}

*::-webkit-scrollbar:vertical {
  border-left: 1px solid #f1f1f1;
}

*::-webkit-scrollbar:horizontal {
  border-top: 1px solid #f1f1f1;
}

*::-webkit-scrollbar-thumb {
  background-color: #c9c9c9;
}

*::-webkit-scrollbar-thumb:hover {
  background-color: #a5a5a5;
}

*::-webkit-scrollbar-thumb:active {
  background-color: #888888;
}

body,
option,
select,
button {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  font-size: 14px;
}

body {
  cursor: default;
  user-select: none;
}

body,
html {
  margin: 0;
  padding: 0;
}

body,
html,
.gui-viewport {
  height: 100%;
  width: 100%;
}

.gui-viewport {
  overflow: hidden;
}
</style>
