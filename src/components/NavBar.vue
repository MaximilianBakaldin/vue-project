<script setup>
    import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
    <div class="nav">
        <div class="logo">AstroSearch</div>
        <ul class="links">
            <li id="l-1"><router-link to="/">Hem</router-link></li>
            <li id="l-2"><router-link to="/about">Om</router-link></li>
        </ul>
    </div>

    <RouterView />
</template>

<style>
    .nav {
        display: flex;
        justify-content: space-around;
        position: fixed;
        z-index: 1;
        color: #f2f2f2;
        font-size: 3rem;
        padding-top: 1rem;
        width: 100%;
        background-color: transparent;
        color: aqua;
    }

    .links {
        display: flex;
        font-size: 1.5rem;
        list-style: none;
    }

    #l-1 {
        padding-right: 5rem;
    }

    #l-2 {
        padding-right: 5rem;
    }

    a {
        color: aqua;
    }
</style>
