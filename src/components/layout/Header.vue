<script setup>
import { RouterLink } from 'vue-router'
</script>
<template>
    <header>
        <div class="center-wr">
            <div class="header">
                <div class="logo">
                    <a href="">LOGO</a>
                </div>
                <div class="menu">
                    <nav>
                        <RouterLink to="/">Home</RouterLink>
                        <RouterLink to="/about">About</RouterLink>
                        <RouterLink to="/contact">Contact</RouterLink>
                        <RouterLink to="/help">Help</RouterLink>
                    </nav>
                </div>
            </div>
        </div>
    </header>
</template>
<style>
header {
    background-color: black;
}

.header {
    display: flex;
    justify-content: space-between;
    padding: 20px 0px;
}

.logo a {
    color: #fff;
    text-decoration: none;
    font-weight: bold;
}

nav {
    display: flex;
    gap: 25px;
}

nav a {
    font-weight: bold;
    text-decoration: none;
    color: #fff;
    transition: .4s;
}

nav a:hover {
    color: #ec6100;
}
</style>