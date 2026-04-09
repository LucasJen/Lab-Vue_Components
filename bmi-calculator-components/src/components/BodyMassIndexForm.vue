<script setup>
import { ref, defineEmits } from 'vue'

const emit = defineEmits(['stats-entered'])

const height = ref(0)
const weight = ref(0)

function statsEntered() {
    // this is called when the button.
    // need to emit an event including the height and weight.
    // the event will be received by the parent compoent of this component.
    // in this app, that's App.vue.
    // in another app, it's whatever the parent is.
    // this component doesn't know and doesn't care where the even goes.
    emit('stats-entered', height.value, weight.value)
}

</script>

<template>
    <div id="bmi-index-form">
        <h2>Enter your height and weight</h2>

        <label for="height">Height</label><input id="height" v-model="height"/>
        <label for="weight">Weight</label><input id="weight" v-model="weight"/>

        <button v-on:click="statsEntered">Calculate!</button>
    </div>
</template>

<style scoped>
#bmi-index-form {
    border: 2px solid grey;
    background-color: salmon;
    color: black;
}
</style>