<template>
  <div class="b-outer">
    <div class="b-top">
      <div class="b-replay">
        <Replay />
      </div>
      <button class="b-button">NEW</button>
    </div>
    <div class="b-bricks">
      <Brick
        v-for="(brick, idx) in bricks"
        :key="idx"
        :idx="brick.idx"
        :active="brick.active"
      />
    </div>
  </div>
</template>

<script>
import Replay from './Replay.vue';
import Brick from './Brick.vue';
export default {
  name: 'Bricks',
  components: { Replay, Brick },
  props: ['randomNumbers'],
  data() {
    return {
      bricks: [...[...Array(9).keys()].map((i) => ({ idx: i, active: false }))],
    };
  },
};
</script>

<style scoped lang="scss">
.b-outer {
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.b-top {
  align-self: center;
  min-width: 72vw;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.b-replay {
  cursor: pointer;
  border: solid 1px #9d9fa2;
  border-radius: 4px;
  padding: 8px;
  width: 64px;
  height: 64px;
  display: flex;
}
.b-button {
  padding: 16px;
  font-size: 32px;
}
.b-bricks {
  align-self: center;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  column-gap: 12px;
  row-gap: 12px;
}
</style>
