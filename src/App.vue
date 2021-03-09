<template>
    <h1>Vue.app</h1>
    <div :class="'app__menu'">
        <button
            v-for="tab in tabs"
            :key="tab"
            class="app__tab-button"
            :class="{ active: currentTab === tab }"
            @click="currentTab = tab"
            v-text="tab"
        />
    </div>
    <div class="app__tab">
        <component v-bind:is="currentTab"></component>
    </div>
</template>

<script>
import NinjaGame from "./components/ninja-reaction/NinjaGame.vue";
import About from "./components/About.vue";

export default {
    name: "App",
    components: { NinjaGame, About },
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
body {
    margin: 0;
    background: #eee;
}
.app__menu {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1px;
}
.app__label {
    font-size: 14px;
}
.app__tab {
    padding: 12px;
    margin: 16px 0;
    min-height: 400px;
    border: 1px solid #ccc;
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
