<script>
    import { store } from "../store.js"
    export default{
        name: 'MainApp',
        data(){
            return {
                store
            }
        }
    }
</script>

<template>
    <div class="container bg-primary text-white">
        <div class="row d-flex justify-content-between">    
            <div class="card  my-4 mx-3 px-2" v-for="film in store.movieSearch" style="width: 18rem;">
                <img src="..." class="card-img-top" alt="ops...">
                <div class="card-body">
                    <h6 class="card-title">Nome: {{ film.title }}</h6>
                    <p class="card-text">Lingua originale:  <img :src=" `/src/assets/img/${film.original_language}.png`" :alt ="film.original_language" class="ms-img"></p>
                    <p class="card-text">Voto: {{ Math.ceil(film.vote_average) }}</p>  
                </div>
            </div>
        </div> 
    </div>  
</template>

<style scoped lang="scss">
    
 .ms-img {
    width: 16px;
    height: 12px;
 }   
</style>