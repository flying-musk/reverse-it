<template>
  <div class="b-grid">
    <div
      class="b-brick"
      :style="{
        gridArea: `${startColumn} / ${startRow} / span 2 / span 2`,
      }"
      :data-active="isActive"
    ></div>
  </div>
</template>

<script>
export default {
  name: 'Brick',
  props: ['idx', 'activeFlag'],
  data() {
    return {
      startColumn: Math.floor(Math.random() * 2) + 1,
      startRow: Math.floor(Math.random() * 2) + 1,
      isActive: false,
    };
  },
  watch: {
    activeFlag: function () {
      this.isActive = true;
      setTimeout(() => {
        this.isActive = false;
      }, 240);
    },
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
  background-color: #f6f6f6;
  transition: 0.48s ease-out;
}
.b-brick[data-active='true'] {
  background-color: #33abd6;
}
.b-brick:active {
  background-color: #33abd6;
}
</style>
