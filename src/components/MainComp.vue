<template>
    <main class="bg-secondary">
        <FilmList :propsArrayFilms2="propsArrayFilms"/>
        <!-- <SeriesList/> -->
    </main>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import FilmList from './FilmList.vue'
// import SeriesList from './SeriesList.vue'

export default {
    name: 'MainComp',
    components: {
    // HelloWorld
        FilmList,
        // SeriesList
    },
    props: {
        propsArrayFilms: Array
    }
}
</script>

<style scoped lang="scss">
    
</style>