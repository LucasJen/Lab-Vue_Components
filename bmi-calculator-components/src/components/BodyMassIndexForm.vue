<script setup>
import { ref, defineEmits } from 'vue'

const emi = defineEmits(['stats-entered'])

const height = ref(0)
const weight = ref(0)

function stats-entered() {
    // this is called when the button.
    // need to emit an event including the height and weight.
    // the event will be received by the parent compoent of this component.
    // in this app, that's App.vue.
    // in another app, it's whatever the parent is.
    // this component doesn't know and doesn't care where the even goes.
    emit('stats-entered')

}

</script>

<template>

    <h2>This is the BMI page</h2>

    <label for="height">Height in meters</label><input id="height" v-model="height"/>
    <label for="weight">Weight in kilograms</label><input id="weight" v-model="weight"/>

    <button v-on:click="calculateBmi">Calculate!</button>

</template>

<style scoped>

</style>