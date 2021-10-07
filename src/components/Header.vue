<template>
	<header class="d-flex bg-black align-items-center justify-content-between">
		<div class="logo">
			<a href="https://fontmeme.com/netflix-font/"><img src="https://fontmeme.com/permalink/211007/c072857f28ffed69c9266a55183f4c20.png" alt="netflix-font" border="0"></a>
		</div>
		<div class="d-flex flex-row align-items-center ">
			<div class="buttons">
				<button class="cerca" @click="$emit('searching', searchFilm)">
					<i class="fas fa-search"></i>
				</button>
				<button class="reset" @click.prevent="reset()">
					<i class="far fa-trash-alt"></i>
				</button>
			<input type="text" v-model="searchFilm">
			
			</div>
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
}
.buttons{
	i{
		color: white;
	}
	.reset, .cerca{
		width: 60px;
		background-color: black;
		color: white;
	}
}
</style>