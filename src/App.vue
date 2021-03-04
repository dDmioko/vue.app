<template>
    <Modal
        v-show="showModal"
        :header="modalHeader"
        :text="modalText"
        @close="toggleModal"
    />
    <h1>{{ title }}</h1>
    <br />
    <button @click="toggleModal">Open modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
    name: "App",
    components: {
        Modal,
    },
    data() {
        return {
            title: "Some new title",
            modalHeader: "Ipsum header",
            modalText: "123",
            showModal: false,
        };
    },
    methods: {
        toggleModal() {
            this.showModal = !this.showModal;
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
    color: #2c3e50;
    margin-top: 60px;
}
h1 {
    border-bottom: 1px solid #ddd;
    display: inline-block;
    padding-bottom: 10px;
}
</style>
