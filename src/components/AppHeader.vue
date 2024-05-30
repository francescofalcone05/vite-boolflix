<script>
import store from '../data/store.js';
import axios from 'axios';



export default {
  components: {
  },

  data() {
    return {
      store,
      cardShow: false,

    }
  },
  methods: {
    getFilmList() {

      const options = {
        method: 'GET',
        url: 'https://api.themoviedb.org/3/search/movie',
        params: { query: this.store.inputValue, language: 'en-US', page: '1' },
        headers: {
          accept: 'application/json',
          Authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJlZDJiNGYwZWY0YjgwZmEwOTBlNzU1OWM5ODNkMzk4ZSIsInN1YiI6IjY2NTczNzRmMDhkM2I5NmJlZTIxNWFkZCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.2RYI6TSOgVLTYH0LBP9wtJR0Rqw_VPkiXHpH7mf9YsE'
        }
      };

      axios
        .request(options)
        .then((response) => {
          this.store.filmList = response.data.results
          //console.log(this.store.filmList);
          for (let index = 0; index < this.store.filmList.length; index++) {
            this.store.filmList[index].cardShow = this.cardShow
            console.log(this.store.filmList);
          }
        })
        .catch(function (error) {
          console.error(error);
        });

    },
    //funzione per mostrare o nascondere la
    // addBol() {
    //   for (let index = 0; index < this.store.filmList.length; index++) {
    //     const element = this.store.filmList[index];
    //     element.push(cardShow = false)
    //     console.log(element);
    //     console.log(this.store.filmList);

    //   }
    // },

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

  <header>
    <div class="logo">
      <h1>BOOLFLIX API</h1>
    </div>

    <div class="input-text">
      <input v-model="store.inputValue" type="text" placeholder="Titolo da cercare">
      <button @click="getFilmList()" type="button">Search</button>
    </div>

  </header>

</template>

<style scoped>
header {
  width: 100%;
  display: flex;
  height: 4rem;
  background-color: black;
  color: red;
  justify-content: space-between;
}

.logo {
  width: 25%;
  height: 100%;
  padding: 1rem;
}

.input-text {
  width: 30%;
  height: 100%;
  align-content: center;
  padding-left: 2rem;
}

input {
  width: 70%;
  padding: 0.1rem;
}

button {
  background-color: red;
  padding: 0.2rem;
}
</style>
