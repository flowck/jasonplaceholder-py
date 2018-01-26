<template>
	<div>
		<h1>Posts</h1>
		<hr>
		<article class="card" v-for="post in posts">
			<div class="card-content">
				<h1 class="title is-4">{{ post.title }}</h1>
				<p> {{ post.body }} </p>
			</div>
		</article>
	</div>
</template>

<script>
	export default {
		name: 'Posts',
		data: () => {
			return {
				posts: []
			}
		},
		created() {
			this.getPosts();
		},
		methods: {
			getPosts() {
				this.$http.get('https://jsonplaceholder.typicode.com/posts')
				.then(
					(success) => {
						this.posts = success.body;
					},
					(error) => {
						console.log(error);
					}
				)
			}
		},
	}
</script>

<style>
	.title{
		text-transform: uppercase;
	}
</style>

