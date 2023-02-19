<script setup></script>

<script>
    export default {
        data() {
            return {
                ImageSource: '/img/rocket-launch-67643_1920.jpeg'
            }
        }
    }
</script>

<template>
    <div>
        <img
            class="rocket-launch"
            v-bind:src="ImageSource"
            alt="rocket launch"
        />
    </div>
</template>

<style scoped>
    .rocket-launch {
        position: relative;
        background-attachment: fixed;
        background-size: cover;
        background-repeat: no-repeat;
        width: 100%;
        height: 100%;
        background-position: center;
    }
</style>
