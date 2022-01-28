<template>
  <div class="b-outer">{{ randomNumbers }}</div>
</template>

<script>
export default {
  name: 'Bricks',
  props: ['randomNumbers'],
};
</script>

<style scoped lang="scss">
.b-outer {
  flex-grow: 1;
  border: solid 1px cornflowerblue;
}
</style>
