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

        <div v-for="film, i in store.filmList" class="card">

            <img @mouseover="" @mouseleave="" :src="store.prefissoImg + film.poster_path" alt="">
            <div class="details">
                <p><span class="red">Titolo:</span> {{ film.title }}</p>
                <p v-if="film.original_title != film.title"><span class="red">Titolo originale:</span> {{
                    film.original_title }}</p>
                <div v-if="film.original_language == 'it'"><span class="red">Lingua:</span><img
                        src="../assets/img/it.svg" alt="">
                </div>
                <div v-if="film.original_language == 'en'"><span class="red">Lingua:</span><img
                        src="../assets/img/en.svg" alt="">
                </div>
                <div v-if="film.original_language == 'fr'"><span class="red">Lingua:</span><img
                        src="../assets/img/fr.svg" alt="">
                </div>
                <div v-if="film.original_language == 'es'"><span class="red">Lingua:</span><img
                        src="../assets/img/es.svg" alt="">
                </div>
                <p><span class="red">Voto:</span>
                    <span><i class="fa-solid fa-star"></i></span>
                    <span><i class="fa-solid fa-star"></i></span>
                    <span><i class="fa-solid fa-star"></i></span>
                    <span><i class="fa-solid fa-star"></i></span>
                    <span><i class="fa-solid fa-star"></i></span>
                    {{ film.vote_average }}
                </p>
            </div>

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

.card>img {
    width: 90%;
}

.details>div>img {
    width: 7%;
    padding-top: 0.1rem;
}

.details>div {
    padding: 0.5rem 0;
}

p {
    margin-bottom: 0.5rem;
    color: gold;
}

p>span {}

.red {
    color: red;
    margin-right: 0.1rem;
}
</style>