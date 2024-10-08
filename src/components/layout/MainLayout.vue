<script setup>
import { RouterView } from 'vue-router';
import Header from "./Header.vue";
import Footer from "./Footer.vue";
</script>

<template>
    <Header />
    <div class="page-content">
        <RouterView />
    </div>
    <Footer />
</template>

<style></style>