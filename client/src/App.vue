<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld v-bind:msg="message" />
  </div>
</template>


<script>
import HelloWorld from "./components/HelloWorld.vue";
import axios from "axios";
export default {
  name: "App",
  components: {
    HelloWorld,
  },
  data: () => ({
    message: "",
  }),
  async created() {
    const {data} = await axios.get(`/api`);
    this.message = data;
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
