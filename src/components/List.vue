<template>
  <div class="block">
    <h1>{{ msg }}</h1>
    <form id="listInput" class="list-container" @submit.prevent="add">
        <input type="text" v-model='listItem'>
        <button type='submit'>Add</button>
    </form>
    <ul id='list'>
		<li v-for="l in list">
    		{{ l }}
  		</li>
	</ul>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    msg: String
  },
  data() {
    return {
      listItem: "",
      list: []
    };
  },
  methods: {
    add() {
	  this.list.push(this.listItem);
	  this.listItem = '';
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.list-container {
  display: flex;
  justify-content: center;
  padding-bottom: 15px;
}

input {
  padding: 15px;
  box-sizing: border-box;
  height: 40px;
}

button {
  height: 40px;
  width: 60px;
  margin-left: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: darkorchid;
  color: white;
}

ul {
	width: 50%;
	margin-left: 40px;
}

li {
	text-align: left;
	margin: 5px auto;
}

</style>
