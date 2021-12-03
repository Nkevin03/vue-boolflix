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
          <ul>
             <li><a href="#">Bambini</a></li>
              <i class="fas fa-bell notification"></i>
              <img src="@/assets/profilo.jpg">
              <i class="fas fa-sort-down arrow"></i>
         </ul>
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
        .search-bar{
            display: flex;
            align-items: center;

            ul{
                display: flex;
                align-items: center;
                margin-bottom: 0;
                list-style: none;
                margin-left: 1rem;

                a{
                    text-decoration: none;
                    color: #fff;
                }

                img{
                    width: 40px;
                }
            }

            i {
                color: #fff;
                font-size: 20px;
                cursor: pointer;

                &:focus input{
                    background: #e50914;
                }
            }   
            .notification{
                padding: 0 20px;
            }
            .arrow{
                font-size: 14px;
                padding: 0 15px;
            }
        }
    }
</style>