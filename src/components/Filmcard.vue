<template>
  <div class="film-card">
    <div>
        <p >Titolo: {{info.title || info.name}}</p>
        <p>Titolo originale: {{info.original_title || info.original_name}}</p>
        <div>
            <span>Language:</span> <img :src="flag(info.original_language)" class="flag-img" >
        </div>
        <p>Voto: {{info.vote_average}}</p>
    </div>
  </div>
  
</template>

<script>
export default {
	name: "Filmcard",
	props: ['info'],
    methods:{
        flag(code) {
            if ( !this.noflag.includes(code) ) {
                return `https://www.unknown.nu/flags/images/${code}-100`;
            } else {
                return "https://upload.wikimedia.org/wikipedia/commons/2/2f/Missing_flag.png";
            }
        }
    },
     data() {
        return {
            noflag : ['gu', 'ii', 'ik', 'iu', 'jv', 'kg', 'ki', 'kj', 'ml', 'mr', 'nb', 'nd', 'ng', 'nn', 'nr', 'pi', 'ps', 'sa', 'sw', 'te', 'tl', 'tw'],
        }
    }
}
</script>
<style lang="scss">
.flag-img{
    width: 40px;
}
</style>