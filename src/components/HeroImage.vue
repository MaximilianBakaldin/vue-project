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

    /* inputValid() gör att den returnerar true om textrutan har något värde. sen bindar du din disabled attribut med !inputValid vilket kommer vara falskt om inputValue är true. den här ```!!this.inputValue``` göra bara om värdet till ett boolean värde. ett utropstecken visar motsatsen (t.ex. om det är true visar den false) och två ger gör samma sak fast igen (alltså visar true om den är true)  */

</style>
