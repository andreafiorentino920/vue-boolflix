<template>
	<header class="d-flex justify-content-center">
		<input type="text" v-model="searchFilm">
		<button @click="$emit('searching', searchFilm)">Cerca</button>
        <button @click.prevent="reset()">Reset</button>
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
</style>