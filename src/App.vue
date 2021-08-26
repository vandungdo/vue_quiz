<template>
  <div id="app">
    <Quiz 
 
      :currentQuestion="quizzes[questionIndex].question"
      :currentAnswers="[...quizzes[questionIndex].incorrect_answers, quizzes[questionIndex].correct_answer]"
    />
    <button
      v-on:click="previousQuestion"
    >
      previous
    </button>
    <button
      v-on:click="nextQuestion"
    >
      next
    </button>
  </div>
</template>

<script>
import Quiz from './components/Quiz.vue'

export default {
  name: 'App',
  data () {
    return {
      quizzes: [],
      questionIndex: 0
    }
  },
  components: {
    Quiz
  },
  mounted () {
      this.$http.get('https://opentdb.com/api.php?amount=10&category=15&difficulty=easy&type=multiple')
      .then(response => {
        this.quizzes = response.data.results
        console.log(this.quizzes)
        
      })
  },
  methods: {
    nextQuestion: function(){
      this.questionIndex ++
    },
    previousQuestion: function(){
      this.questionIndex --
    }
  }
}
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
</style>
