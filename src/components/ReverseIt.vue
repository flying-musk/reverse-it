<template>
  <div id="reverse_it">
    <h1>Reverse it</h1>
    <p>Identify the number string and reverse it.</p>
    <div class="r-main">
      <Bricks :randomNumbers="randomNumbers" @new="newRandomNumbersFlag++" />
      <Answer :randomNumbers="randomNumbers" />
    </div>
  </div>
</template>

<script>
import Bricks from './Bricks.vue';
import Answer from './Answer.vue';
export default {
  name: 'ReverseIt',
  components: { Bricks, Answer },
  data() {
    return {
      numbersSource: [
        ...[...Array(9).keys()].map((i) => i + 1),
        ...[...Array(9).keys()].map((i) => i + 1),
      ],
      randomNumbers: [],
      newRandomNumbersFlag: 0,
      MIN_AMOUNT: 4,
      MAX_AMOUNT: 6,
    };
  },
  watch: {
    newRandomNumbersFlag: {
      immediate: true,
      handler() {
        this.randomNumbers = this.numbersSource
          .sort(() => Math.random() - 0.5)
          .slice(0, 9);
      },
    },
  },
};
</script>

<style scoped lang="scss">
.r-main {
  display: flex;
  flex-direction: column;
  gap: 16px;
}
</style>
