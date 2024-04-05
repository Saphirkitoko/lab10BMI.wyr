<script setup>

// Importing ref and watch functions from vue
import { ref, watch } from 'vue'

//defining props for the component
defineProps({
question:string,
  answer1:string,
  answer2:string,
})
const emit = defineEmits(['answer-selected'])

const choice =ref("")

watch(choice, () =>{ emit('answer-selected', choice.value)})

</script>

<template>
  <div id="wyr">
<h2>make your choice!</h2>
  <p>{{ question }}</p>
  <div>
<!-- radio buttons for selecting answers-->
  <input v-model="choice" v-bind:value="Answer1" type="radio" id="answer-1">
  <label for="answer-1">{{ answer1 }}</label>
  <input v-model="choice" v-bind:value="answer2" type="radio" id="answer-2">
  <label for="answer-2">  {{ Answer2 }}</label>
  </div>
  </div>


</template>

<style scoped>

/* style for component */
#wyr { background-color: purple;}
p {font-family: Corbel Light;}

</style>
