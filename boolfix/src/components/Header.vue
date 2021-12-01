<template>
  <header class="d-flex justify-content-between align-items-center">
     <div class="nav-left">
        <h1>BOOLFIX</h1>
        <ul>
            <li><a href="#"><b>Home</b></a></li>
            <li><a href="#">Serie TV</a></li>
            <li><a href="#">Film</a></li>
            <li><a href="#">Nuovi e popolari</a></li>
            <li><a href="#">La mia lista</a></li>
        </ul>
     </div>
     <div class="search-bar">
          <input type="text" v-model="watch" @keyup.enter="$emit('Searching', watch), ClearBar()" placeholder="Cerca Film o Serie">
         <i class="fas fa-search" @click="$emit('Searching', watch), ClearBar()"></i>
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

        .nav-left{
            display: flex;

            ul{
                display: flex;
                align-items: center;
                list-style: none;
                margin-bottom: 0;

                li{
                    padding: 0 10px;
                }

                a{
                text-decoration: none;
                color: #fff;
                }
            }
        }

        h1{
            color: #e50914;
            margin-bottom: 0;
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
        .search-bar i{
            color: #fff;
            font-size: 20px;
            cursor: pointer;
        }
    }
</style>