<template>
	<div>
		<article class="card" v-for="post in posts">
			<div class="card-content">
				<h1 class="title is-4">
					<a :href="'/posts/' + post.id"> {{ post.title }} </a>
				</h1>
				<p> {{ post.body }} </p>
			</div>
		</article>
		
		<div class="space"></div>

		<button class="button is-primary">Load more posts</button>

		<div class="space"></div>
	</div>
</template>

<script>
	export default {
		name: 'Posts',
		data: () => {
			return {
				posts: [],
				allPosts: [],
				loadPosition: 0,
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
				
						// Iterate the array of posts and return only 10
						// posts.
						for(let i = 0; i < success.body.length; i++) {
							if(i < 10){
								// Save 10 posts in posts array
								this.posts.push(success.body[i]);
								// Load position to fetch later when load more // is called
								this.loadPosition = i;
							}
						}

					},
					(error) => {
						console.log(error);
					}
				)
			},
			loadMorePosts() {

			}
		},
	}
</script>

<style>
	.title{
		text-transform: uppercase;
	}
</style>

