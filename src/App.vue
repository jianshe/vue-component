<template>
  <div id="app">
    <Tree></Tree>
    <!-- <KFormTest></KFormTest> -->
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" foo="foo"
      ref="hw">
    <template v-slot:default>abc</template>
    <template v-slot:contnet="slotProps">content...{{slotProps.xx}}</template>
    <template v-slot:content="{xx}">content...{{xx}}</template>
    </HelloWorld> -->
    <!-- 组件通信 -->
    <!-- <Communicate></Communicate> -->
    <!-- 插槽 -->
    <!-- <SlotTest></SlotTest> -->
    <!-- 递归 -->
    <!-- <Recursion></Recursion> -->
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Communicate from "@/components/communicate";
import Tree from "@/components/tree"
// import SlotTest from "@/components/slots";
// import Recursion from "@/components/recursion";
// import KFormTest from "@/components/form";

export default {
  name: "app",
  provide() {
    return {
      something: "something"
    };
  },
  components: {
    Tree
  },
  mounted() {
    // this.$refs.hw.xx = "xxx"; // 修改子类中data对象中定义的属性。
    // this.$children[0].xx = "xxxxx"; // 修改子类中data对象中定义的属性。
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
