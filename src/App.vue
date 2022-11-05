<template>
  <div id="app">

    <h1>Would you rather?</h1>

    <WouldYouRather v-for="question in questions" v-bind:key="question" v-bind:question= "question"
 
    v-on:answer-changed="answerChanged"></WouldYouRather>

    <p>You would rather...{{choice}}</p>

  </div>
</template>

<script>
import WouldYouRather from './components/WouldYouRather.vue'

export default {
  name: 'App',
  components: {
    WouldYouRather
  },
  data(){
    return{
      //make a list of questions in an array
      questions : [
            { 
              id : 0,
              question: 'live in a house shaped like a triangle or a house shaped like a circle?',
              answer1: 'Live in a triangle house',
              answer2: 'Live in a circle house',
            
            },

            { 
              id : 1,
              question: 'be a wizard or a superhero?',
              answer1: 'Be a wizard',
              answer2: 'Be a superhero',
          
            },

            { 
              id : 2,
              question: 'have an elephant-sized cat or a cat-sized elephant?',
              answer1: 'Have an elephant-sized cat',
              answer2: 'Have a cat-sized elephant',
              //userSelectionMessage= ''
            }
        ]
      }
    },
    methods:{
      answerChanged(choice, id){
        this.userSelectionMessage = `Thanks! you chose ${choice}`

      }
    }
}
</script>

<style>

body{
  background: radial-gradient(rgb(97, 97, 203), rgb(115, 198, 115),yellow);
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #502c43;
  margin-top: 60px;
  padding: 10px;
  margin-top: 70px;
  background: bluebiolet;
}

p{
  font-style: italic;
  font-size: 30px;
}
</style>
