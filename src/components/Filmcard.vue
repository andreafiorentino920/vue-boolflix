<template>
  <section>
	<p>Titolo: {{film.title}}</p>
	<p>Titolo originale: {{film.original_title}}</p>
	<p>Lingua: {{film.original_language}}</p>
	<p>Voto: {{film.vote_average}}</p>
  </section>
</template>

<script>
export default {
	name: "Filmcard",
	props: ['film']
}
</script>

<style>
</style>