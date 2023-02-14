<template>
    <div class="greeting">
        <h2>HejHej {{ name }}</h2>
    </div>
</template>

<script>
    export default {
        props: ['name']
    }
</script>

<style>
    .greeting {
        background-clip: text;
        -webkit-background-clip: text;
        color: transparent;
        background-image: linear-gradient(
            to right,
            #c300ff,
            #004cff,
            #00ff00,
            #ff8000,
            #ff0008,
            #ff00ff
        );
        -webkit-background-image: linear-gradient(
            to right,
            #c800ff,
            #ffff00,
            #00ff00,
            #00ffff,
            #0000ff,
            #ff00ff
        ); /* kopierad kod från w3schools för att få en gradient color scheme */
        font-size: 3rem;
        display: flex;
        justify-content: center;
    }
</style>
