<template>
	<header class="d-flex bg-black align-items-center justify-content-between">
		<div class="logo">
			<a href="https://fontmeme.com/netflix-font/"><img src="https://fontmeme.com/permalink/211007/c072857f28ffed69c9266a55183f4c20.png" alt="netflix-font" border="0"></a>
		</div>
		<div class="buttons d-flex align-items-center">
			<button class="cerca" @click="$emit('searching', searchFilm)">
				<i class="fas fa-search"></i>
			</button>
			<input type="text" v-model="searchFilm" placeholder="Quale film cerchi?">
			<button class="reset" @click.prevent="reset()">
				<i class="far fa-trash-alt"></i>
			</button>
			<span class="utente"><img class="utente-img" src="../assets/avatar.png" alt=""><i class="fas fa-sort-down"></i></span>Andrea
		</div>
	</header>
</template>

<script>
export default {
	name: "Header",
	data() {
		return {
			searchFilm: ""
		}
	},
    methods:{
        reset(){
        this.searchFilm = "";
        this.$emit("search", this.searchFilm)
      }
    }
}
</script>
	
<style lang="scss">
header{
	height: 15vh;
	.logo{
		margin-left: 20px;
	}
	.buttons{
		color: white;
		margin-right: 20px;
		.utente{

			i{
				font-size: 20px;
				margin:0 5px 0 15px;
			}
		}
		.reset, .cerca{
			width: 60px;
			background-color: black;
			color: white;
		}
		img{
			margin-left: 25px;
			width: 50px;
		}
}
}

</style>