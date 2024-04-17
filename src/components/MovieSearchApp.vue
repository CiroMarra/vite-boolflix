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
    <div class="container py-3">
        <div class="input-group">
            <input type="text" v-model="store.movieInput" placeholder="Titolo del film...">
            <button type="button" @click="$emit('searchFilm')">Cerca</button>
        </div>
    </div>
</template>

<style scoped lang="scss">

</style>