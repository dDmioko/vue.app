<template>
    <h1>Ninja Reaction Timer</h1>
    <button @click="onNinjaStart" :disabled="showNinjaGame">Play</button>
    <Block v-if="showNinjaGame" :delay="delay" @close="onNinjaClose" />
    <Results v-if="showResults" :score='score' />
</template>

<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";

export default {
    name: "App",
    components: { Block, Results },
    data() {
        return {
            showNinjaGame: false,
            showResults: false,
            delay: null,
            score: null,
        };
    },
    methods: {
        onNinjaStart() {
            this.delay = 2000 + Math.random() * 5000;
            this.showNinjaGame = true;
            this.showResults = false;
        },
        onNinjaClose(result) {
            this.showNinjaGame = false;
            this.score = result;
            this.showResults = true;
        },
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #444;
    margin-top: 60px;
}
</style>
