<template>
  <div class="film-card">
    <div>
        <p>Titolo: {{film.title}}</p>
        <p>Titolo originale: {{film.original_title}} </p>
        <p>Lingua: {{film.original_language}}</p>
        <p>Voto: {{film.vote_average}}</p>
    </div>
  </div>
  
</template>

<script>
export default {
	name: "Filmcard",
	props: ['film','serie']
}
</script>
<style lang="scss">
</style>