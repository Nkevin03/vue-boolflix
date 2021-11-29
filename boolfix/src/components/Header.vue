<template>
  <header>
      <input type="text" v-model="watch" @keyup.enter="$emit('Searching', watch), ClearBar()">
      <button @click="$emit('Searching', watch), ClearBar()">Search</button>
  </header>
</template>

<script>

export default {
    name: 'Header',
    data() {
		return {
			watch: '',
		};
	},
	methods: {
		ClearBar() {
			this.watch = '';
		},
	},
}
</script>

<style scoped lang="scss">
    header{
        margin: 10px;
    }
</style>