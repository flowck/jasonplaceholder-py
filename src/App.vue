<template>
	<div id="app">
		<!-- Header start here -->
		<header class="main-header container">
			<div class="page-title">
				<h1>
					<a href="/">Jasonplaceholder</a>
				</h1>
			</div>
		</header>
		<!-- Header ends here -->
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
	
	header .page-title{
		font-size: 40px;
		text-align: center;
		font-family: 'Satisfy', cursive;
	}

	header .page-title a{
		text-decoration: none;
	}

	.space{
		width: 100%;
		height: 40px;
	}

	.container{
		width: 800px;
		margin: 0 auto;
	}
</style>
