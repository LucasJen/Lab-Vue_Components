<script setup>
import { ref, watch } from 'vue'
import BodyMassIndexForm from './components/BodyMassIndexForm.vue';

const bmi = ref(null) // Falsy value
const useMetric = ref(false)

// watch the useMetric checkbox to see if it is checked
watch(useMetric, () => {bmi.value = null})

function calculateBmi(height, weight) {
  // determine which math to use depending on useMetric value
  if (useMetric.value) {
    bmi.value = weight / (height * height)
  } else {
    bmi.value = (weight / (height * height)) * 730
  }
}

</script>

<template>
  <div id="bmi-app">
  <h1>Body Mass Index Calculator</h1>
  <label> Use Metric Units
    <input type="checkbox" v-model="useMetric" />
  </label>
  <BodyMassIndexForm v-on:stats-entered="calculateBmi"/>

  <!-- updated bmi to round to nearest hundredths place -->
  <p v-if="bmi">Your BMI is: {{ bmi.toFixed(2) }}</p>
  <p v-else>Please enter data in the form</p>
  </div>
</template>

<style scoped>

</style>