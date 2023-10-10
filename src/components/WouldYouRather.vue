<script setup>
import { ref } from 'vue'

defineProps({
  question: String,
  answer1: String,
  answer2: String
})

const emit = defineEmits( [
  'answer-selected'
])

const choice = ref('')

function choiceMade() {
  emit('answer-selected', choice.value)
}

</script>

<template>

<div id="wyr">

  <h2>Make your choice!</h2>

  <div id="question">
    {{ question }}
  </div>

  <div id="answers">
    <input type="radio" id="answer-1" v-model="choice" v-bind:value="answer1" v-on:change="choiceMade">
    <label for="answer-1"> {{ answer1 }}</label>

    <input type="radio" id="answer-2" v-model="choice" v-bind:value="answer2" v-on:change="choiceMade">
    <label for="answer-2"> {{ answer2 }}</label>
  </div>

</div>
</template>

<style scoped>

#wyr {
  background-color: hotpink;
  padding: 20px;
}

#answers {
  padding: 10px;
}

</style>


