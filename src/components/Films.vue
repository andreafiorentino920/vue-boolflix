<template>
	<div class="container-films d-flex flex-column">
		<div class="films film">
			<ul class="container d-flex flex-wrap">
				<li class="col-2 container" v-for="(film, index) in films" :key="index">
					<Filmcard :info="film"/>
				</li>
			</ul>
		</div>
		<div class="films serie">
			<ul class="container d-flex flex-wrap">
				<li class="col-2 container" v-for="(serie, index) in series" :key="index">
					<Filmcard :info="serie"/>
				</li>
			</ul>
		</div>
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
		width: 25%;
	}
}
</style>