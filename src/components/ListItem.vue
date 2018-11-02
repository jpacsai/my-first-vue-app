<template>
	<li>
        <span>•</span>
        <p>{{ text }}</p>
        <button @click='remove(ListItem)'>Delete</button>
	</li>
</template>

<script>
export default {
	name: "ListItem",
	props: ['ListItem', 'text'],
	data() {
		return {
			isActive: true
		};
	},
	methods: {
		remove(l) {
			this.$emit('remove', l);
		}
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
