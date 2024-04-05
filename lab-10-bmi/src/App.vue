<script setup>

// Importing the wouldyourather component from its file
import WouldYouRather from './components/WouldYouRather.vue'
import {ref} from 'vue'

// Creating reactive variables for the question and answers
const wyrQuestion = ref('live in the house shaped like a triangle or a house shaped like like circle')
const wyrAnswer1 = ref('triangle house')
const wyrAnswer2 = ref('circle house')



const userselection = ref('')
function UpdateUserSelection(userChoice) {
  userselection.value = `Thanks! you chose ${userChoice}`
}
</script>

<template>
  <div id="app-component">
<h1>Would You Rather?</h1>
    <!--rendering the wouldyourather component-->
  <WouldYouRather
    v-bind:question="wyrQuestion"
    v-bind:answer1="wyrAnswer1"
    v-bind:answer2="wyrAnswer2"
    v-on:answer-selected="updateUserselection"
    ></WouldYouRather>
  <p>{{userselection}}</p>
  </div>
</template>

<style scoped>
/*style for the components*/
#app-component { background-color: aqua;
padding:40px;}
p {font-family: fantasy;}

</style>
