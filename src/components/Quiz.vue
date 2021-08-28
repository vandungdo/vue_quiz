<template>
  <div class="quiz">

      <b-container fluid>
        <!-- Question -->
        <b-row align-h="center">
          <b-col cols="8">{{currentQuestion}}</b-col>  
        </b-row>
        <!-- Answers list -->
        <br>
        <b-row 
          align-h="center"
          v-for="answer in currentAnswers"
          :key="answer.id"
        >
          <b-col cols="4">
            <b-input-group class="mb-4">
              <b-input-group-default is-text
                
              >
                <input type="checkbox" aria-label="Checkbox for following text input">
              </b-input-group-default>
              {{answer}}
            </b-input-group>
          </b-col>
        </b-row>
      </b-container>
  </div>
</template>

<script>
export default {
  name: 'Quiz',
  props: {
      currentQuestion: [],
      currentAnswers: []
  },
  
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
