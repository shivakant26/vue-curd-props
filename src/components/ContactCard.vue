<script setup>
const props = defineProps(["name", "age"])
</script>
<template>
    <div class="center-wr">
        <div class="card">
            <h2>name : {{ name }}</h2>
            <p>age : {{ age }}</p>
        </div>
    </div>
</template>
<style scoped>
.card {
    width: 25%;
    display: inline-block;
    margin: 15px;
    padding: 15px;
    box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.5);
    border-radius: 5px;
}
</style>