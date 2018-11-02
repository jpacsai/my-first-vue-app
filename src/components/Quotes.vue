<template>
	<div class="block">
		<h1>{{ msg }}</h1>
		<h3>Chuck Norris jokes</h3>
		<p id="quotes">{{ this.quote }}</p>
		<button @click='getQuote'>Get a new joke</button>
	</div>
</template>

<script>
	export default {
	name: "Quotes",
	props: {
		msg: String
	},
	data() {
		return {
		quote: ""
		};
	},
	methods: {
		getQuote() {
		fetch("https://api.chucknorris.io/jokes/random")
			.then(data => data.json())
			.then(data => this.quote = data.value);
		}
	},
	created: function() {
		this.getQuote();
	}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
	.block {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	h3 {
		margin: 0;
	}

	p {
		box-sizing: border-box;
		width: 280px;
		line-height: 1.4;
		background-color: white;
		padding: 15px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	button {
		width: 165px;
	}
</style>
