<script>

import store from '../data/store.js';
import axios from 'axios';



export default {
    components: {
    },

    data() {
        return {
            store,

        }
    },
    methods: {

    },
    created() {

    },
    mounted() {

    },
    computed: {

    },
}

</script>

<template>

    <div class="contenitore">

        <div v-for="film in store.filmList" class="card">
            <img :src="store.prefissoImg + film.poster_path" alt="">
            <p><span>Titolo:</span> {{ film.title }}</p>
            <p><span>Titolo originale:</span> {{ film.original_title }}</p>
            <p><span>Lingua:</span> {{ film.original_language }}</p>
            <p><span>Voto:</span> {{ film.vote_average }}</p>


        </div>

    </div>

</template>

<style scoped>
.contenitore {
    width: 80%;
    margin: 2rem auto;
    display: flex;
    flex-wrap: wrap;
}

.card {
    width: calc(100% / 6);
    min-height: 20rem;
    padding: 1rem;
}

img {
    width: 90%;
}

p {
    margin-bottom: 0.5rem;
}

span {
    color: red;
}
</style>