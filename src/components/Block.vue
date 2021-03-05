<template>
    <div v-if="showBlock" class="block" @click="stopTimer">Click me</div>
</template>

<script>
export default {
    props: ["delay"],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0,
        };
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true;
            this.startTimer();
        }, this.delay);
    },
    methods: {
        startTimer() {
            const ms = 10;
            this.reactionTime = 0;
            this.timer = setInterval(() => {
                this.reactionTime += ms;
            }, ms);
        },
        stopTimer() {
            clearInterval(this.timer);
            this.showBlock = false;
            this.$emit("close", this.reactionTime);
        },
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
