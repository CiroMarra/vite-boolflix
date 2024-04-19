<script>
    import { store } from "../store.js";
    import SeriesApp from "./SeriesApp.vue";
    import MoviesApp from "./MoviesApp.vue";
    

    export default{
        name: 'MainApp',
        components: {
            SeriesApp,
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
        <MoviesApp></MoviesApp>
        <SeriesApp></SeriesApp>
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