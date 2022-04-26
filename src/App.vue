<template>
  <div id="app">
    <HeaderComp @ricerca="funRicercaFilms" />
    <MainComp :propsArrayFilms="films"/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
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
        films: []
      };
  },
  
  components: {
    HeaderComp,
    MainComp
  },

  methods: {
      funRicercaFilms(testoCercato){

        let films = []

        axios.get(`http://api.themoviedb.org/3/search/movie?api_key=${this.apiKey}&query=${testoCercato}&language=it-IT`)
        .then( (res)=> {
        // console.log(res.data.results)
        this.films = res.data.results
        // films.push(res.data.results)
        })
        console.log(films)
        

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
