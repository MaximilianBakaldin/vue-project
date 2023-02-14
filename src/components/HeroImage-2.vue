<script setup></script>

<script>
    export default {
        data() {
            return {
                ImageSource2: '/img/raisting-satellite-1010862_1920.jpeg'
            }
        }
    }
</script>

<template>
    <div>
        <img class="satellite" v-bind:src="ImageSource2" alt="satellite" />
    </div>
</template>

<style scoped>
    .satellite {
        background-image: linear-gradient(
            rgba(0, 0, 0, 0.9),
            rgba(0, 0, 0, 0.1)
        );
        background-color: black;
        position: relative;
        background-attachment: fixed;
        background-size: cover;
        background-repeat: no-repeat;
        width: 100%;
        height: 100%;
        background-position: center;
    }
</style>
