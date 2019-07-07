<template>
  <div>
    <div>{{first}} 와 {{second}} 의 곱은?</div>
    <form @submit.prevent="checkAnswer">
      <input type="text" v-model="answer" ref="answer" />
      <button>정답확인</button>
    </form>
    <p>{{result}}</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      first: null,
      second: null,
      answer: null,
      result: null
    };
  },
  mounted() {
    this.startGame();
  },
  methods: {
    checkAnswer() {
      let right = this.first * this.second;
      if (right === parseInt(this.answer)) {
        this.result = "정답입니다.";
        setTimeout(() => {
          this.startGame();
        }, 500);
      } else {
        let self = this;
        this.result = "오답입니다.";
        setTimeout(() => {
          self.answer = null;
          self.result = null;
          self.$refs.answer.focus();
        }, 500);
      }
    },
    startGame() {
      this.first = this.getRandomNum();
      this.second = this.getRandomNum();
      this.answer = null;
      this.result = null;
      this.$refs.answer.focus();
    },
    getRandomNum() {
      return Math.ceil(Math.random() * 9);
    }
  }
};
</script>