<template>
    <h1>Vue.app</h1>
    <button
        v-for="tab in tabs"
        :key="tab"
        class="app__tab-button"
        :class="{ active: currentTab === tab }"
        @click="currentTab = tab"
        v-text="tab"
    />
    <br />
    <div class="app__tab">
        <component v-bind:is="currentTab"></component>
    </div>
</template>

<script>
import NinjaGame from "./components/ninja-reaction/NinjaGame.vue";

export default {
    name: "App",
    components: { NinjaGame },
    data() {
        return {
            currentTab: null,
            tabs: ["NinjaGame", "About"],
        };
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
.app__tab {
    border: 1px solid #ccc;
    padding: 12px;
    margin: 16px 0;
}
.app__tab-button {
    padding: 6px 10px;
    border-top-left-radius: 3px;
    border-top-right-radius: 3px;
    border: 1px solid #ccc;
    cursor: pointer;
    background: #f0f0f0;
    margin-bottom: -1px;
    margin-right: -1px;
}
.app__tab-button:hover {
    background: #e0e0e0;
}
.app__tab-button.active {
    background: #e0e0e0;
}
</style>
