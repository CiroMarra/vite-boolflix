<script>
    import { store } from "../store.js";

    import MoviesApp from "./MoviesApp.vue";
    

    export default{
        name: 'MainApp',
        components: {
            MoviesApp,
        },

        data(){
            return {
                store,
                flag: ['it', 'en', 'ja']
            }
        },
    }
</script>

<template>
    <div class="container bg-primary text-white">
        <div class="container">
            <div class="row d-flex">

                    <h1>Film</h1>
                    <MoviesApp v-for="film in store.movieSearch" :films="film"></MoviesApp>

                    <h1>Series</h1>
                    <MoviesApp v-for="series in store.seriesSearch" :films="series"></MoviesApp>

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