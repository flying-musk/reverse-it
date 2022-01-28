<template>
  <div id="app">
    <ReverseIt />
  </div>
</template>

<script>
import ReverseIt from './components/ReverseIt.vue';
export default {
  name: 'App',
  components: { ReverseIt },
};
</script>

<style lang="scss">
body {
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
}
</style>
