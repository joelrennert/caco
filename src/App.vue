<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
export default {
  name: 'App',
}
</script>

<style>
.router-view {
  transition: opacity 2s ease-in-out;
  opacity: 0;
}

.router-view-enter-active,
.router-view-leave-active {
  transition: opacity 2s ease-in-out;
}

.router-view-enter, .router-view-leave-to {
  opacity: 0;
}
</style>