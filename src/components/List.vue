<template>
<div class="block">
	<h1>{{ msg }}</h1>
	<form id="listInput" class="list-container" @submit.prevent="add">
		<input type="text" v-model='listItem'>
		<button type='submit'>Add</button>
	</form>
	<ul id='list'>
		<li v-for="l in list" :key="l.id">
			<span>{{ l.text }}</span>
			<button>Delete</button>
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
      list: [],
      id: 0
    };
  },
  methods: {
    add() {
      const listObj = {
        text: this.listItem,
        id: this.id
      };
      this.list.push(listObj);
      this.listItem = "";
      this.id++;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
form {
  align-items: center;
  display: grid;
  grid-template: 100% / 200px 80px;
  padding-bottom: 15px;
  justify-content: center;
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
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
}

li {
  text-align: left;
  display: grid;
  grid-template: 100% / 200px 80px;
  margin: 5px auto;
  justify-content: center;
}

span {
	display: flex;
    align-items: center;
}
</style>
