<script>
    import { store } from "../store.js";
    export default{
        name: 'MoviesApp',
        props: {
            films: Object
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
            <div class="card  my-4 mx-3 px-2 "  style="width: 18rem;">
                <img :src="`https://image.tmdb.org/t/p/w342${films.poster_path}`" alt="" class="ms-sfi-mg">
                <div class="card-body bg-danger">
                    <h6 class="card-title">Nome: {{ films.title || films.name }}</h6>
                    <small>Titolo originale {{ films.original_title || films.original_name }}</small>
                    <div v-if="flag.includes(films.original_language)">
                        <p class="card-text">Lingua originale: <img :src="getImageUrl(films.original_language)" class="ms-img"></p>
                    </div>
                    <div v-else>
                        Lingua originale: {{ films.original_language }}
                    </div>   
                    <p class="card-text">Voto: {{ Math.ceil(films.vote_average) }}</p>  
                </div>
            </div>
</template>

<style scoped lang="scss">
    
 .ms-img {
    width: 16px;
    height: 12px;
 }   

 .ms-sfi-mg {
    object-fit:fill;
    width: 270px;
    height: 300px;
 }
</style>