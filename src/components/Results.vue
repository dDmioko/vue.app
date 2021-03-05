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
    /* width: 400px;
    border-radius: 20px;
    background: #0faf87; */
    color: #0faf87;
    text-align: center;
    /* padding: 100px 0;
    margin: 40px auto; */
}
</style>
