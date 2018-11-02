<template>
	<li>
        <span>•</span>
        <p>{{ text }}</p>
        <button @click='remove(l)'>Delete</button>
	</li>
</template>

<script>
export default {
	name: "ListItem",
	props: {
		text: String
	},
	data() {
		return {
			isActive: true
		};
	},
	methods: {
		remove(l) {
			const listIndex = this.list.indexOf(l);
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
