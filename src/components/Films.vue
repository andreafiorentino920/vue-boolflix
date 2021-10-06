<template>
  <div class="container d-flex justify-content-center">
	<ul>
		<li v-for="(film, index) in films" :key="index">
			<Filmcard :film="film"/>
		</li>
		<ul>
		<li v-for="(serie, index) in series" :key="index">
			<Filmcard :serie="serie"/>
		</li>
	</ul>
	</ul>
  </div>
</template>

<script>
import Filmcard from './Filmcard.vue';
export default {
	name: "Films",
	props: ['films','series'],
	components: {
		Filmcard
	}
}
</script>

<style lang="scss">
</style>