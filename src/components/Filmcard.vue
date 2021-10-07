<template>
<div :style="{ backgroundImage: 'url(https://image.tmdb.org/t/p/w300'+info.poster_path+')'}" class="film-card">
    <div class="info">
    <p>Titolo: {{info.title || info.name}}</p>
    <p>Titolo originale: {{info.original_title || info.original_name}}</p>
    <div>
        <span>Language:</span> <img :src="flag(info.original_language)" class="flag-img" >
    </div>
    <div class="star">
        Voto: 
        <i v-for="n in 5" :key="n"
        class="fa-star"
        :class="(n <= vote(info.vote_average)) ? 'fas' : 'far'"
        > </i>
    </div>
    <p>Overview: {{info.overview}}</p>
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
.film-card{
    color: white;
    height: 450px;
    overflow-y: scroll;

    .info{
        height: 100%;
        display: none;
        
    }
    .info:hover{
        display: block;
        background-color: black;
    }
    .flag-img{
    width: 40px;

    .star{
        i{
        color: gold;
        }
    }
    }
}


</style>