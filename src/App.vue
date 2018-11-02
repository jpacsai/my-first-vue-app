<template>
  <div id="app">
    <Counter msg="Counter"/>
    <List msg="List"/>
  </div>
</template>

<script>
import Counter from './components/Counter.vue';
import List from './components/List';

export default {
  name: 'app',
  components: {
    Counter,
    List
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.block {
  width: 400px;
  padding: 15px;
  background-color: lavender;
  margin: 15px;
}

h3 {
  margin: 40px 0 0;
}

input, button, submit {
  border: none;
} 

button {
  background-color: darkorchid;
  color: white;
}

button:active {
  background-color: rgb(72, 15, 100);
}
</style>
