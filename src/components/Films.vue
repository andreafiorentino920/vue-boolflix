<template>
  <div class="container d-flex justify-content-center">
	<ul>
		<li v-for="(film, index) in films" :key="index">
			<Filmcard :film="film"/>
		</li>
	</ul>
  </div>
</template>

<script>
import Filmcard from './Filmcard.vue';
export default {
	name: "Films",
	props: ['films'],
	components: {
		Filmcard
	}
}
</script>

<style>
</style>