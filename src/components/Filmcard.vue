<template>
  <div class="film-card">
	<p>Titolo: {{film.title}}</p>
	<p>Titolo originale: {{film.original_title}}</p>
	<p>Lingua: {{film.original_language}}</p>
	<p>Voto: {{film.vote_average}}</p>
  </div>
</template>

<script>
export default {
	name: "Filmcard",
	props: ['film, serie']
}
</script>

<style>
</style>