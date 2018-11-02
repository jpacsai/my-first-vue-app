<template>
	<li @click='complete'>
        <span>•</span>
        <p :class="{ crossed: isActive }">{{ text }}</p>
        <button @click='remove(ListItem)'>Delete</button>
	</li>
</template>

<script>
export default {
	name: "ListItem",
	props: ['ListItem', 'text'],
	data() {
		return {
			isActive: false
		};
	},
	methods: {
		remove(l) {
			this.$emit('remove', l);
		},
		complete() {
			this.isActive = !this.isActive;
		}
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
	button {
		height: 40px;
		width: 80px;
		margin-left: 10px;
		display: flex;
		align-items: center;
		justify-content: center;
		color: white;
	}

	li {
		text-align: left;
		display: grid;
		grid-template-columns: 30px 170px 100px;
		margin: 5px auto;
		justify-content: center;
	}

	p, span {
		display: flex;
		align-items: center;
		overflow: auto;
	}

	p {
		cursor: pointer;
	}

	.crossed {
		text-decoration: line-through;
		color: grey;
	}
</style>
