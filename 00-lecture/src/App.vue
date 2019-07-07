<template>
  <div id="app">
    <h2>{{ msg }}</h2>
    <Test />
    <Gugudan />
  </div>
</template>

<script>
import Gugudan from "./components/Gugudan.vue";
export default {
  components: { Gugudan },
  data() {
    return {
      msg: "Hello Vue"
    };
  }
};
</script>
<style>
html,
body {
  margin: 0;
  padding: 0;
}

#app {
  width: 500px;
  margin: 0 auto;
}
</style>

