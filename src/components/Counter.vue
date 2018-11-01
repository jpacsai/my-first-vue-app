<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <button @click="doStuff">Click</button>
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
</style>
