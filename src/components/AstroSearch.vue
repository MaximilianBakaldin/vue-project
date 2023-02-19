<script setup></script>

<template>
    <div class="input" style="position: absolute; z-index: 200">
        <h2 class="text">Search for a specific astronaut!</h2>
        <input class="input-text" type="text" v-model="search" />
        <button type="button" class="btn" @click="fetchApi">Search</button>
        <ul>
            <li v-for="astronaut in astronauts">
                <template
                    v-if="
                        astronaut.name
                            .toLowerCase()
                            .includes(search.toLowerCase())
                    "
                >
                    <!-- kopierad kod från chatGPT (.toLowerCase().includes(search.toLowerCase())) angående hur man gör så att texten i sökrutan inte blir case sensitive -->
                    <p class="result">Name: {{ astronaut.name }}</p>
                    <p class="result">Age: {{ astronaut.age }}</p>
                    <p class="result">Biography: {{ astronaut.bio }}</p>
                </template>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                search: '',
                astronauts: []
            }
        },
        methods: {
            async fetchApi() {
                const response = await fetch(
                    `https://ll.thespacedevs.com/2.2.0/astronaut/?search=${encodeURIComponent(
                        this.search
                    )}`
                ) /* kopierad kod från chatGPT (encodeURIComponent) angående hur man får det så att texten i sökrutan kopplas till api:et så att rätt namn dyker upp i sökresultaten */
                const data = await response.json()
                this.astronauts = data.results
            }
        }
    }
</script>

<style scoped>
    .input {
        margin-top: 30vh;
        margin-top: -50rem;
    }

    .input-text {
        border-radius: 0.5rem;
        border-color: transparent;
        padding: 0.5rem 1rem;
        margin-left: 37rem;
    }

    .btn {
        border-radius: 0.5rem;
        padding: 0.5rem 1rem;
        margin-left: 0.25rem;
        border-color: transparent;
        cursor: pointer;
    }

    .text {
        margin-top: 20vh;
        margin-left: -5vw;
        font-size: 2rem;
        color: aqua;
        margin-left: 32rem;
    }

    .result {
        color: aqua;
    }
</style>
