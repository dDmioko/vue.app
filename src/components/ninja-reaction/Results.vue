<template>
    <p>Score: {{ score }} ms</p>
    <p class="results__rank">{{ rank }}</p>
</template>

<script>
export default {
    props: ["score"],
    data() {
        return {
            rank: null,
        };
    },
    mounted() {
        if (this.score < 250) {
            this.rank = "Ninja Fingers";
        } else if (this.score < 400) {
            this.rank = "Rapid reflexes";
        } else {
            this.rank = "Snail pace...";
        }
    },
};
</script>

<style>
.results__rank{
    font-size: 24px;
    font-weight: bold;
    color: #0faf87;
}
</style>
