<template>
  <div class="content d-flex flex-wrap">
		<div class="card" v-for="movie in movies" :key="`${movie.title}`">
			<Card 
                  :image="movie.backdrop_path"
                  :title="movie.title"
                  :subTitle="movie.original_title"
                  :text="movie.original_language"
                  :number="movie.vote_average"
              />
		</div>

        <div class="card" v-for="serie in series" :key="`${serie.title}`">
			<Card 
                :image="serie.backdrop_path"
                :title="serie.name"
                :subTitle="serie.original_name"
                :text="serie.original_language"
                :number="serie.vote_average"
            />
		</div>
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
    .content{
        background-color: #141414;
    }
    .card{
        position: relative;
        height: 400px;
        display: flex;
        align-items: center;
        text-align: center;
        width: calc(100% / 6);
        margin: 30px;
        border-radius: 10px;
    }
</style>