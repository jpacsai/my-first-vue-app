<template>
<div class="block">
	<h1>{{ msg }}</h1>
	<form id="listInput" class="list-container" @submit.prevent="add">
		<input type="text" v-model='listItem' required>
		<button type='submit'>Add</button>
	</form>
	<ul id='list'>
		<ListItem 
			v-for="ListItem in list" v-bind:key="ListItem.id"
			v-bind:id="ListItem.id"
			v-bind:text="ListItem.text"
			v-bind:ListItem="ListItem"
			v-on:remove="remove" />
	</ul>
</div>
</template>

<script>
import ListItem from "./ListItem";

export default {
	name: "List",
	components: {
		ListItem
  	},
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
		},
		remove(ListItem) {
			const listIndex = this.list.indexOf(ListItem);
			this.list.splice(listIndex, 1);
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
		grid-template-columns: 30px 170px 80px;
		margin: 5px auto;
		justify-content: center;
	}

	p, span {
		display: flex;
		align-items: center;
		overflow: auto;
	}
</style>
