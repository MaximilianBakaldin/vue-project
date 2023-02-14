<script setup>
    import HelloHi from '../components/HelloHi.vue'
</script>

<template>
    <div class="input">
        <h1 class="text" style="position: absolute; z-index: 100">
            Click the button to generate astronauts!
        </h1>
        <button type="button" class="btn" @click="fetchApi">Search</button>
        <HelloHi name="Richard" />

        <ul>
            <li v-for="astronaut in astronauts">
                <p class="result">Name: {{ astronaut.name }}</p>
                <p class="result">Age: {{ astronaut.age }}</p>
                <p class="result">Biography: {{ astronaut.bio }}</p>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                astronauts: []
            }
        },
        methods: {
            async fetchApi() {
                const response = await fetch(
                    'https://ll.thespacedevs.com/2.2.0/astronaut/?format=json&limit=50'
                )
                const data = await response.json()
                this.astronauts = data.results
            }
        },
        props: ['name']
    }
</script>

<style scoped>
    .btn {
        border-radius: 1rem;
        padding: 1rem 3rem 1rem 3rem;
        font-size: 2rem;
        border: transparent;
        position: absolute;
        left: 42vw;
        top: 42vh;
        cursor: pointer;
    }

    .text {
        margin-top: -90vh;
        margin-left: 32vw;
        color: aqua;
    }

    .result {
        color: aqua;
    }
</style>
