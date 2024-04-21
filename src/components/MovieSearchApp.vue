<script>
    import { store } from '../store.js';

    export default{
        name: 'MovieSearchApp',
        data(){
            return {
                store,
            }
        }
    }
</script>

<template>
    <nav class="navbar navbar-expand-lg">
        <div class="container-fluid ms-border">
            <img src="../assets/img/logo.png" alt="">
            <form class="d-flex" role="search">
                <input class="form-control me-2" type="text" v-model="store.movieInput" placeholder="Titolo del film..." aria-label="Search">
                <button class="btn btn-outline-danger"type="button" @click="$emit('searchFilm')">Cerca</button>
            </form>
        </div>
    </nav>

</template>

<style scoped lang="scss">

</style>