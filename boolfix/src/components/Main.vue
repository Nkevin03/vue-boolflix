<template>
  <div>
		<div v-for="movie in movies" :key="`${movie.title}`">
			<h2>{{movie.title}}</h2>
			<p>{{movie.original_title}}</p>
			<p>{{movie.original_language}}</p>
			<p>{{movie.vote_average}}</p>
		</div>
	</div>
</template>

<script>
export default {
    name: 'Main',
    props: {
		movies: Array,
	},
}
</script>

<style scoped lang="scss">

</style>