<template>
  <div id="app">
    <div class="lista">
      <Collapse
        v-for="example in examples"
        :key="example.id"
        :example="example"
        :inside="false"
      />
    </div>
  </div>
</template>

<script>
import Collapse from "./components/Collapse.vue";
import examples from "./examples";
import "@squidit/css/dist/css/squid.min.css";

export default {
  name: "App",
  components: {
    Collapse,
  },
  data() {
    return {
      examples,
    };
  },
};
</script>

<style>
#app {
  width: 100vw;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
.lista {
  display: grid;
}
</style>
