<template>
  <div id="app">
    <Counter msg="Counter"/>
    <List msg="ToDo List"/>
		<Quotes msg="Random Jokes API" />
  </div>
</template>

<script>
import Counter from "./components/Counter.vue";
import List from "./components/List";
import Quotes from "./components/Quotes";

export default {
  name: "app",
  components: {
    Counter,
		List,
		Quotes
  }
};
</script>

<style>
	#app {
		font-family: "Avenir", Helvetica, Arial, sans-serif;
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
		background-color: #c769f6;
		color: white;
		cursor: pointer;
		height: 40px;
		margin: 10px;
		padding: 0;
		display: flex;
		align-items: center;
		justify-content: center;
		font-size: 120%;
	}

	button:hover {
		background-color: darkorchid;
	}

	button:active {
		background-color: rgb(72, 15, 100);
	}

	::-webkit-scrollbar {
    height: 8px;
		width: 8px;
	}

	/* Track */
	::-webkit-scrollbar-track {
		background: #f1f1f1; 
	}
	
	/* Handle */
	::-webkit-scrollbar-thumb {
		background: #888; 
	}

	/* Handle on hover */
	::-webkit-scrollbar-thumb:hover {
		background: #555; 
}
</style>
