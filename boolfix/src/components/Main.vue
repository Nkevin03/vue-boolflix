<template>
  <div>
		<ul v-for="movie in movies" :key="`${movie.title}`">
			<Card 
                  :image="movie.backdrop_path"
                  :title="movie.title"
                  :subTitle="movie.original_title"
                  :text="movie.original_language"
                  :number="movie.vote_average"
              />
		</ul>

        <ul v-for="serie in series" :key="`${serie.title}`">
			<Card 
                :image="serie.backdrop_path"
                :title="serie.name"
                :subTitle="serie.original_name"
                :text="serie.original_language"
                :number="serie.vote_average"
            />
		</ul>
	</div>
</template>

<script>
import Card from '@/components/Card';
export default {
    name: 'Main',
    props: {
		movies: Array,
		series: Array,
	},
    components: {
        Card,
    },
}
</script>

<style scoped lang="scss">
    img{
        width: 30px;
    }
</style>