<template>
    <main class="bg-secondary">
        <FilmList :propsArrayFilms2="propsArrayFilms"/>
        <SeriesList :propsArraySerie2="propsArraySerie"/>
    </main>
</template>

<script>
import FilmList from './FilmList.vue'
import SeriesList from './SeriesList.vue'

export default {
    name: 'MainComp',
    components: {
        FilmList,
        SeriesList
    },
    props: {
        propsArrayFilms: Array,
        propsArraySerie: Array
    }
}
</script>

<style scoped lang="scss">
    
</style>