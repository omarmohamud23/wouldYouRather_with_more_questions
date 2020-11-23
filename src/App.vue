<template>
  <div id="app">
    <h1>Would You Rather??</h1>

      <would-you-rather-with-more-components 
       v-for="question in questions"
       v-bind:question="question.wyrQuestion"
       v-bind:answer1="question.wyrAnswer1"
      v-bind:answer2="question. wyrAnswer2"
       v-bind:id = "question.id "
      v-on:answer-changed="answerChanged">
      </would-you-rather-with-more-components>

      <p>You Would Rather...</p>

      <ul v-for="answer in answers" > 
        <li>{{ answer }}</li>
      </ul>

    
  </div>
</template>

<script>
import WouldYouRatherWithMoreComponents from './components/WouldYouRatherWithMoreComponents.vue'

export default {
  name: 'App',
  components: {
    WouldYouRatherWithMoreComponents
  },
  data () {
    return {
      questions: [
     
     {
       id: 0,
       wyrQuestion: 'Would you rather be able to control fire or water?',
      wyrAnswer1: 'Fire',
      wyrAnswer2: 'Water',
      userSelectionMessage: ''
     },
     {
       id:1,
       wyrQuestion: 'Would you rather be really good at math or really good at sports?' ,
       wyrAnswer1: 'Math',
       wyrAnswer2: 'Sports',
       userSelectionMessage: ''
     },
    {
      id:2,
      wyrQuestion: 'Would you rather meet your favorite celebrity or be on a TV show?' ,
     wyrAnswer1: 'Favorite celebrity',
     wyrAnswer2: 'Tv show',
     userSelectionMessage: '' 
    }  
      ]
    }
  },
  methods: {
    answerChanged(choice) {
     this.userSelectionMessage = `Thanks! You chose ${choice}`
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

  background-color: aquamarine;
  border:blue
}
</style>
