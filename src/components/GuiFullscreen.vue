<template>
  <div class="gui-viewport">
    <slot />
  </div>
</template>

<style>
* {
  box-sizing: border-box;
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
