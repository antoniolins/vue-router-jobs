<template>
	<div v-if="job">
		<h1>{{ job.title }}</h1>
		<p>{{ job.details }}</p>
		<p>
			Lorem ipsum dolor, sit amet consectetur adipisicing elit. Officiis magni, laudantium quos molestiae assumenda numquam? Autem eum laudantium
			beatae sint placeat, a repellat corporis, omnis, excepturi odit atque veritatis voluptates? Ipsum ducimus id dolor, corrupti maxime sit quos,
			ullam placeat sunt, hic aut ex iusto neque esse quibusdam laboriosam! Accusamus, sit dolor aspernatur commodi magnam officiis unde eius fugit
			aliquid suscipit vitae, tempore possimus nisi labore, architecto ipsam debitis quod incidunt sunt. Eum, voluptas quia quod iste sunt
			voluptatibus qui fugiat reprehenderit, officiis repudiandae repellat, dolorum odio accusamus ut error unde quaerat non beatae quae rerum officia
			ipsa? Facere, ratione.
		</p>
	</div>
	<div v-else>
		<p>Loading job details...</p>
	</div>
</template>

<script>
	export default {
		props: ['id'],
		data() {
			return {
				job: null,
			};
		},
		mounted() {
			fetch('http://localhost:3000/jobs/' + this.id)
				.then((res) => res.json())
				.then((data) => (this.job = data))
				.catch((err) => console.log(err.message));
		},
	};
</script>

<style></style>
