<template>
	<div id="app">
		<header class="main-header container">
			<h1>JSONPLACEHOLDER</h1>
		</header>
		<div class="container">
			<router-view/>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'App'
	}
</script>

<style>
	/* Global CSS */
	@import '../node_modules/bulma/css/bulma.css';
	
	.container{
		width: 800px;
		margin: 0 auto;
		border: 1px solid red;
	}
</style>
