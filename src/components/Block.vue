<template>
    <div v-if="showBlock" class="block" @click="onClick">Click me</div>
</template>

<script>
export default {
    props: ["delay"],
    data() {
        return {
            showBlock: false,
        };
    },
    methods: {
        onClick() {
            this.showBlock = false;
            this.$emit("close");
        },
    },
    created() {
        setTimeout(() => {
            this.showBlock = true;
        }, this.delay);
        // console.log(this.delay);
    },
};
</script>

<style>
.block {
    width: 400px;
    border-radius: 20px;
    background: #0faf87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
}
</style>
