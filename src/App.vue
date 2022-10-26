<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <p id="hello">안녕하세요</p>
  <HelloWorld msg="Welcome to Your Vue.js App" />
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #1567b9;
  margin-top: 60px;
}

#hello {
  color: red;
  font-weight: 300px;
  font-size: 50px;
}
</style>
