<template>
  <div id="app">
    <Header @Searching="Search"/>
		<Main id="Body" :movies="movies" :series="series"/>
  </div>
</template>

<script>

import axios from'axios'
import Header from '@/components/Header.vue'
import Main from '@/components/Main.vue'
export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data() {
		return {
			movies: [],
			series: [],
		};
	},
	methods: {
		Search(title) {
			if (title !== '') { {
				axios.get('https://api.themoviedb.org/3/search/movie?', {
					params: {
						api_key: 'f137419f4e1c495ea896066f72846878',
						query: title,
						language: 'it',
					},
				})
				.then((response) => {
					this.movies = response.data.results;
					console.log(this.movies);
				})
				.catch(function (error) {
					console.log(error);
				}),

				axios.get('https://api.themoviedb.org/3/search/tv', {
					params: {
						api_key: 'f137419f4e1c495ea896066f72846878',
						query: title,
						language: 'it',
					},
				})
				.then((response) => {
					this.series = response.data.results;
					console.log(this.series);
				})
				.catch(function (error) {
					console.log(error);
				})
			}
			}
		},
	},
}
</script>

<style lang="scss">
@import '@/styles/global.scss';
</style>
