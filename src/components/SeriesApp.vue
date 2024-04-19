<script>
    import { store } from "../store.js";
    

    export default{
        name: 'SeriesApp',

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
        <div class="row d-flex"> 
            <h2>Serie TV</h2> 
            <div class="card  my-4 mx-3 px-2" v-for="series in store.seriesSearch" style="width: 18rem;">
                <img :src="`https://image.tmdb.org/t/p/w342${series.poster_path}`" alt="" class="ms-sfi-mg">
                <div class="card-body bg-danger">
                    <h6 class="card-title">Nome: {{ series.title }}</h6>
                    <div v-if="flag.includes(series.original_language)">
                        <p class="card-text">Lingua originale: <img :src="getImageUrl(series.original_language)" class="ms-img"></p>
                    </div>
                    <div v-else>
                        Lingua originale: {{ series.original_language }}
                    </div>   
                    <p class="card-text">Voto: {{ Math.ceil(series.vote_average) }}</p>  
                </div>
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