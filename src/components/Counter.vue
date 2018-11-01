<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="counter-container">
      <button @click="doStuff">-</button>
      <div class="display"></div>
      <button @click="doStuff">+</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Counter',
  props: {
    msg: String
  },
  methods: {
    doStuff () {
      alert('Did something!')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}

input, button, submit {
  border: none;
} 

.counter-container {
  display: flex;
  align-items: center;
  justify-content: center;
}

.display, button {
  width: 40px;
  height: 40px;
  margin: 10px;
}

.display {
  background-color: lightgray;
}

button {
  background-color: aquamarine;
}
</style>
