<template>
  <div class="film-card">
    <div>
        <div class="">
            <img :src="`https://image.tmdb.org/t/p/w154${info.poster_path}`" alt="">
        </div>
        <p>Titolo: {{info.title || info.name}}</p>
        <p>Titolo originale: {{info.original_title || info.original_name}}</p>
        <div>
            <span>Language:</span> <img :src="flag(info.original_language)" class="flag-img" >
        </div>
        <div>
            <i v-for="n in 5" :key="n"
            class="fa-star"
            :class="(n <= vote(info.vote_average)) ? 'fas' : 'far'"
            ></i>
        </div>
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
        },
        vote(num){
            num = (num/2);
            return num = Math.ceil(num)
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
i{
    color: gold;
}
</style>