<script>
     import axios from "axios";
    import MovieSearchApp from "./components/MovieSearchApp.vue";
    import MainApp from "./components/MainApp.vue";
    import { store } from "./store.js";

    export default{
        components: {
          MovieSearchApp,
            MainApp,
        },
        data(){
            return {
                store,
            }
        },
        methods: {
            getMoviesFromApi(){
                const qParams = {
                    api_key: "d4dcb1bd2440284f714100f1ddc7645f",
                    query: store.movieInput
                }

                axios.get("https://api.themoviedb.org/3/search/movie", { params: qParams })
                .then((response) => {
                    store.movieSearch = response.data.results
                })
            }
        }
    }
</script>

<template>
  <MovieSearchApp @searchFilm="getMoviesFromApi"></MovieSearchApp>
  <MainApp></MainApp>
</template>

<style lang="scss">

</style>