<script>
    import { store } from "../store.js";
    import MediaVote from "./MediaVote.vue";
    export default{
        name: 'MoviesApp',
        components: {
            MediaVote
        },
        props: {
            films: Object,
        },

        data(){
            return {
                store,
                flag: ['it', 'en', 'ja']
            }
        },

        methods: {
            getImageUrl(flag) {
                return `./src/assets/img/${flag}.png`;
            }
        }
    }
</script>

<template>
    <div class="card my-4 mx-3" style="width: 18rem;">
        <div class="card-body">
            <h6 class="card-title">Nome: {{ films.title || films.name }}</h6>
            <small>Titolo originale: {{ films.original_title || films.original_name }}</small>
            <div v-if="flag.includes(films.original_language)">
                <p class="card-text">Lingua originale: <img :src="getImageUrl(films.original_language)" class="ms-img"></p>
            </div>
            <div v-else>
                Lingua originale: {{ films.original_language }}
            </div>   
            <p class="card-text">Voto: <MediaVote :vote="films.vote_average"></MediaVote></p> 
        </div>
        <img :src="`https://image.tmdb.org/t/p/w342${films.poster_path}`" alt="" class="ms-sfi-mg">
        <div class="overlay"></div>
    </div>
</template>

<style scoped lang="scss">
.ms-img {
    width: 16px;
    height: 12px;
}

.ms-sfi-mg {
    object-fit: fill;
    width: 270px;
    height: 500px;
}

.card {
    position: relative;
    background-color: transparent;
    border: none;
}

.overlay {
    position: absolute;
    top: 0;
    width: 94%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7); 
    opacity: 0; 
    transition: opacity 0.3s ease;
}

.card:hover .overlay {
    opacity: 1; 
}

.card-body {
    position: absolute;
    top: 28%; 
    left: 35%;
    transform: translate(-50%, -50%);
    color: white; 
    display: none;
    z-index: 2;
}

.card:hover .card-body {
    display: block; 
}
</style>