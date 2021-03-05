<template>
    <h2 class="result">Score: {{ score }} ms</h2>
</template>

<script>
export default {
    props: ["score"],
};
</script>

<style>
.result {
    color: #0faf87;
    text-align: center;
}
</style>
