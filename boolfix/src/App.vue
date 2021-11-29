<template>
  <div id="app">
    <Header @startSearching="performSearch"/>
		<Main id="Body" :movies="movies"/>
  </div>
</template>

<script>
// import Axios from "axios";
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
		};
	},
	methods: {
		performSearch(title) {
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
			})
		},
	},
}
</script>

<style lang="scss">
@import '@/styles/global.scss';
</style>
