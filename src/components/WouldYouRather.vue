<template>
  <div class="wyr">
    <!-- display the questions and options here -->
    <h2>Would you rather...</h2>

    <h3>...{{question.question}}</h3>
    
    <input type="radio" v-model="choice" v-bind:value="question.answer1" v-on:change="choiceMade">
    <label>{{question.answer1}}</label>

    <input type="radio" v-model="choice" v-bind:value="question.answer2" v-on:change="choiceMade">
    <label>{{question.answer2}}</label>

  </div>
</template>

<script>
export default {
  name: 'WouldYouRather',
  props: {
    question: Object //this will be an object
    
  },
  data(){
    return{
      choice: ''
    }
  },
  methods:{
    choiceMade() {
      //emit an event 'answer-changed' and include the value of the data choice
      this.$emit('answer-changed',this.question.id, this.choice)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 15px 0 0;
}

.wyr{
  border: 2px black solid;
  background: linear-gradient(rgb(224, 172, 181), rgb(212, 127, 212))
}

</style>
