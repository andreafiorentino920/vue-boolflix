<template>
  <div class="container films d-flex justify-content-center">
	<ul class="container d-flex flex-wrap justify-content-center">
		<li class="col-2" v-for="(film, index) in films" :key="index">
			<Filmcard :info="film"/>
		</li>
	</ul>
	<ul class="container d-flex flex-wrap justify-content-center">
		<li class="col-2" v-for="(serie, index) in series" :key="index">
			<Filmcard :info="serie"/>
		</li>
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

<style lang="scss" scoped>
.films{

	li{
		margin-top: 30px;
		margin-bottom: 30px;
	}
}
</style>