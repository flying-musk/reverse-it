<template>
  <div class="a-outer" @click="answerClick">
    <template v-if="answerFlag % 3 === 0">
      <div class="a-title">Answer</div>
    </template>
    <template v-if="answerFlag % 3 === 1">
      <div class="a-title" v-for="(number, idx) in randomNumbers" :key="idx">
        {{ number }}
      </div>
    </template>
    <template v-if="answerFlag % 3 === 2">
      <div
        class="a-title"
        v-for="(number, idx) in reversedRandomNumbers"
        :key="idx"
      >
        {{ number }}
      </div>
    </template>
  </div>
</template>

<script>
export default {
  name: 'Answer',
  props: ['randomNumbers'],
  data() {
    return { answerFlag: 0 };
  },
  computed: {
    reversedRandomNumbers: function () {
      return JSON.parse(JSON.stringify(this.randomNumbers)).reverse();
    },
  },
  methods: {
    answerClick() {
      this.answerFlag++;
    },
  },
};
</script>

<style scoped lang="scss">
.a-outer {
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 16px;
}
.a-title {
  font-size: 64px;
}
</style>
