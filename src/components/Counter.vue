<template>
  <div class="block">
    <h1>{{ msg }}</h1>
    <div class="counter-container">
      <button @click="decr">-</button>
      <div class="display">{{ count }}</div>
      <button @click="incr">+</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Counter',
  props: {
    msg: String
  },
  data () {
    return {
      count: 0
    }
  },
  methods: {
    decr () {
      this.count -= 1
    },
    incr () {
      this.count += 1
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
  display: flex;
  align-items: center;
  justify-content: center;
}

.display {
  background-color: white;
}

button {
  background-color: darkorchid;
  color: white;
}
</style>
