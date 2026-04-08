<script setup>
import BodyMassIndexForm from './components/BodyMassIndexForm.vue';

</script>

<template>
  <h1>This is App.vue</h1>

  <BodyMassIndexForm v-on:stats-entered="calculateBmi"/>
</template>
