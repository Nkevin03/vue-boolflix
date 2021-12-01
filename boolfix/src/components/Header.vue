<template>
  <header class="d-flex justify-content-between align-items-center">
      <h1>BOOLFIX</h1>
     <div class="search-bar">
          <input type="text" v-model="watch" @keyup.enter="$emit('Searching', watch), ClearBar()" placeholder="Cerca Film o Serie">
         <button @click="$emit('Searching', watch), ClearBar()">Cerca</button>
     </div>
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
        background-color: #000;
        padding: 10px;

        h1{
            color: #e50914;
        }


        input {
          border: 0;
          border-bottom: 2px solid grey;
          outline: 0;
          font-size: 1.3rem;
          color: white;
          background: transparent;
        }
        input[type=text]:focus {
           border-color: #e50914;
           transition: 0.5s;

        }
        button{
            background-color: #e50914;
            outline: none;
            border: 0;
            margin: 0 10px;
            color: #fff;
            height: 31px;
            width: 85px;
            border-radius: 25px;
        }
    }
</style>