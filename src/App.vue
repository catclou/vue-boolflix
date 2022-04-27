<template>
  <div id="app">
    <HeaderComp @ricerca="funRicercaFilms" />
    <MainComp id="main" :propsArrayFilms="films" :propsArraySerie="serie"/>
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
import "bootstrap"
import axios from 'axios'


export default {
  name: 'App',
  data() {
      return {
        testoCercato: '',
        apiKey: 'dd24b1cfe827ceabdc1afbe01d042a08',
        films: [],
        serie: []
      };
  },
  
  components: {
    HeaderComp,
    MainComp
  },

  methods: {
      funRicercaFilms(testoCercato){

        // ricerca di film 
        axios.get(`http://api.themoviedb.org/3/search/movie?api_key=${this.apiKey}&query=${testoCercato}&language=it-IT`)
        .then( (res)=> {
        this.films = res.data.results
        })
        
        // ricerca di serie
        axios.get(`http://api.themoviedb.org/3/search/tv?api_key=${this.apiKey}&query=${testoCercato}&language=it-IT`)
        .then( (res)=> {
        this.serie = res.data.results
        })

      }
  },
}
</script>

<style lang="scss">

@import "bootstrap/dist/css/bootstrap.min.css";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

</style>
