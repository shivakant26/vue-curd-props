<script setup>
const props = defineProps(["title"])
</script>
<template>
    <h1>I am : {{ title }}</h1>
    <button @click="$emit('increaseCount', 11)">click me</button>
</template>
<style></style>