<template>
  <div>
		<div v-for="movie in movies" :key="`${movie.title}`">
			<h2>{{movie.title}}</h2>
			<p>{{movie.original_title}}</p>
			<span v-if="!languageimg.includes(movie.original_language)">{{ movie.original_language}}</span>
				<img v-else :src="require(`@/assets/${movie.original_language}.png`)" :alt="languageimg">
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
    data() {
		return {
			languageimg: ['it', 'en'],
		};
	},
}
</script>

<style scoped lang="scss">
    img{
        width: 30px;
    }
</style>