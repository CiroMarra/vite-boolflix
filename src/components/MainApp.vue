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
            <div class="card  my-4 mx-3 px-2" v-for="films in store.movieSearch" style="width: 18rem;">
                <img src="..." class="card-img-top" alt="ops...">
                <div class="card-body">
                    <h6 class="card-title">Nome: {{ films.title }}</h6>
                    <p class="card-text">Lingua originale:  <img :src=" `/src/assets/img/${films.original_language}.png`" :alt ="films.original_language" class="ms-img"></p>
                    <p class="card-text">Voto: {{ Math.ceil(films.vote_average) }}</p>  
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