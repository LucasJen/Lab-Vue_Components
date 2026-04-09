<script setup>
import { ref } from 'vue'

import BodyMassIndexForm from './components/BodyMassIndexForm.vue';

const bmi = ref() // Falsy value

function calculateBmi(height, weight) {

  let bmiValue = weight / (height * height)
  bmi.value = bmiValue
}

</script>

<template>
  <h1>This is App.vue</h1>

  <BodyMassIndexForm v-on:stats-entered="calculateBmi"/>

  <p v-if="bmi">Your BMI is: {{ bmi }}</p>
  <p v-else>Please enter data in the form</p>

</template>
