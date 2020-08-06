<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import { createElement } from "../src/utils/valculator/element";
import { renderDom } from "../src/utils/valculator/element";
export default {
  name: "App",
  components: {
    // HelloWorld,
  },
  mounted() {
    this.VDOMFunction();
  },
  methods: {
    VDOMFunction() {
      let V_DOM = createElement("ul", { class: "list" }, [
        createElement("li", { class: "item" }, ["item1"]),
        createElement("li", { class: "item" }, ["item2"]),
        createElement("li", { class: "item" }, ["item3"]),
      ]);

      console.log(V_DOM);
      var el = renderDom(V_DOM);
      console.log(el);
      document.body.appendChild(el); // 向elemente最后一个节点后添加此内容
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
</style>
