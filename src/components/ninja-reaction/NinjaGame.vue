<template>
    <h2>Ninja Reaction Timer</h2>
    <button @click="onNinjaStart" :disabled="showNinjaGame">Play</button>
    <Block v-if="showNinjaGame" :delay="delay" @close="onNinjaClose" />
    <Results v-if="showResults" :score='score' />
</template>

<script>
import Block from "./Block.vue";
import Results from "./Results.vue";

export default {
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
