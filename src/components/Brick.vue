<template>
  <div class="b-grid">
    <div
      class="b-brick"
      :style="{
        gridArea: `${startColumn} / ${startRow} / span 2 / span 2`,
      }"
    ></div>
  </div>
</template>

<script>
export default {
  name: 'Brick',
  props: ['idx', 'active'],
  data() {
    return {
      startColumn: Math.floor(Math.random() * 2) + 1,
      startRow: Math.floor(Math.random() * 2) + 1,
    };
  },
};
</script>

<style scoped lang="scss">
.b-grid {
  display: grid;
  grid-template-columns: repeat(3, 36px);
  grid-template-rows: repeat(3, 36px);
  column-gap: 4px;
  row-gap: 4px;
}
.b-brick {
  border-radius: 4px;
  background-color: #0096cc;
}
</style>
