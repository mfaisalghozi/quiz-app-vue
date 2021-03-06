<template>
  <div id="app">
    <Header :numCorrect="numCorrect" :numTotal="numTotal" />
    <b-container class="bv-example-row full-screen">
      <b-row class="full-screen">
        <b-col sm="6" offset="3" class="full-screen">
          <QuestionBox
            v-if="questions.length"
            :currentQuestion="questions[index]"
            :next="next"
            :increment="increment"
            v-show="index <= 9"
          />
          <Closing v-show="index >= 10" />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import Header from "./components/Header";
import QuestionBox from "./components/QuestionBox";
import Closing from "./components/Closing";

export default {
  name: "App",
  components: {
    Header,
    QuestionBox,
    Closing,
  },
  data() {
    return {
      questions: [],
      index: 0,
      message: "Hello",
      numCorrect: 0,
      numTotal: 0,
    };
  },
  methods: {
    next() {
      this.index++;
    },
    increment(isCorrect) {
      if (isCorrect) {
        this.numCorrect++;
      }
      this.numTotal++;
    },
  },
  mounted: function () {
    fetch("https://opentdb.com/api.php?amount=10&type=multiple", {
      method: "get",
    })
      .then((res) => {
        return res.json();
      })
      .then((jsonData) => {
        console.log(jsonData.results);
        this.questions = jsonData.results;
      });
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.full-screen {
  height: 89vh;
}
</style>
