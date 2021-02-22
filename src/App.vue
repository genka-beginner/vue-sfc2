<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld
    :msg="title"
    :count="num"
    @child-event="parentEvent"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";
import RefLinks from "./components/HelloWorld.vue";
import CopyDocs from "./components/HelloWorld.vue";

export default defineComponent({
  name: "App",
  components: {
    HelloWorld,
    RefLinks,
    CopyDocs,
  },
  setup() {
    const title = ref("Welcome to Your Vue.js + TypeScript App");
    const num = ref(0);
    const parentEvent = (newVal: number) => {
      num.value = newVal;
    };
    return { title, num, parentEvent };
  },
});
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
</style>
