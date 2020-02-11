<template>
  <div id="app">
    <h1>Quiz</h1>
    <div class="component">
      <component :is="currentComponent" @changeMode="currentComponent = $event"/>
    </div>
  </div>
</template>

<script>
import Correct from "@/components/correct";
import Incorrect from "@/components/incorrect";
import Questions from "@/components/questions";

export default {
  components: {
    Correct,
    Incorrect,
    Questions
  },
  data() {
    return {
      currentComponent: "Questions"
    };
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  position: relative;
  height: 100vh;
}
</style>
<style scoped>
.component {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  height: 230px;
  width: 400px;
  display: flex;
  align-items: center;
}
h1 {
  text-align: center;
}
</style>

