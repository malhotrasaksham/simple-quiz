<template>
  <div class="container">
    <span>
      <h2>Incorrect Answer!</h2>
    </span>
    <button @click="$emit('changeMode', 'Questions')">Next Question</button>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.container {
  background-color: #fab0b0;
  height: 100%;
  width: 100%;
  padding: 20px;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
}
.container span {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
}
.container button {
  padding: 10px;
  color: #FFF;
  background-color: #0072bc;
  border: none;
  cursor: pointer;
}
</style>
