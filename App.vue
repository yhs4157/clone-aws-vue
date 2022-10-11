<script setup>
import {refer} from 'vue'

const mst = ref('hello world')
</script>

<template>
    <h1>{{msg}}</h1>
    <input v-model="msg">
</template>