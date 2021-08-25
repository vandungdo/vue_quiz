<template>
  <div id="app">
    <Quiz 
      :currentQuestion="questions"
    />
  </div>
</template>

<script>
import Quiz from './components/Quiz.vue'

export default {
  name: 'App',
  data () {
    return {
      questions: '',
      answers: null
    }
  },
  components: {
    Quiz
  },
  mounted () {
      this.$http.get('https://opentdb.com/api.php?amount=10&category=15&difficulty=easy&type=multiple')
      .then(response => {
        return this.questions = response.data.results[0].question
      })
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
