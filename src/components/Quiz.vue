<template>
  <div class="quiz">
      {{currentQuestion}}
      <br>
      <ul class="ul-no-bullets">
        <li 
          v-for="answer in currentAnswers"
          :key="answer.id"
        >
          <input type="checkbox">
          {{answer}}
        </li>
      </ul>
  </div>
</template>

<script>
export default {
  name: 'Quiz',
  props: {
      currentQuestion: [],
      currentAnswers: []
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  ul.ul-no-bullets {
    list-style-type: none;
    padding: 0;
    margin: 0;
  }
</style>
