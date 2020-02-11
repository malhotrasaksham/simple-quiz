<template>
  <div class="container">
    <div class="question">{{questions[currentQuestion].question}}</div>
    <div class="options">
      <div
        class="option"
        v-for="(option, index) in questions[currentQuestion].options"
        :key="index"
        @click="ValidateAnswer(index)"
      >{{index + 1}}). {{option}}</div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      questions: [
        {
          question: "Where is Taj Mahal?",
          options: ["Agra", "Noida", "Delhi", "Jaipur"],
          answer: 0
        },
        {
          question: "What is the formula for Water?",
          options: ["H2S", "H3O", "H2O", "H2O2"],
          answer: 2
        },
        {
          question: "What is the formula for pythagoras theorem?",
          options: [
            "A^2 + B^2 = C",
            "A^2 + B^2 = C^2",
            "A^2 + B^2 = C^4",
            "A + B = C"
          ],
          answer: 1
        }
      ]
    };
  },
  computed: {
    currentQuestion() {
      return Math.floor(Math.random() * this.questions.length);
    }
  },
  methods: {
    ValidateAnswer(answer) {
      if (this.questions[this.currentQuestion].answer === answer)
        this.$emit("changeMode", "Correct");
      else this.$emit("changeMode", "Incorrect");
    }
  }
};
</script>
<style scoped>
.container {
  background-color: #F0F0F9;
  display: flex;
  flex-direction: column;
  padding: 20px;
  box-sizing: border-box;
  width: 100%;
  height: 100%;
}
.question {
  flex: 1;
  font-weight: bold;
  font-size: 1.2em;
}
.options {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.option {
  display: inline-block;
  width: 45%;
  padding: 10px;
  background-color: #0072bc;
  cursor: pointer;
  box-sizing: border-box;
  color: #FFF;
  font-weight: bold;
  margin: 10px 0px;
}
</style>

