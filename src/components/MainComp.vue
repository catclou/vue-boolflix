<template>
    <main>
        <h1>Ciao, sono il main</h1>
        <FilmList/>
        <SeriesList/>
    </main>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import FilmList from './FilmList.vue'
import SeriesList from './SeriesList.vue'

export default {
    name: 'MainComp',
    components: {
    // HelloWorld
    FilmList,
    SeriesList
    }
}
</script>

<style scoped lang="scss">
    main {
        background-color: burlywood;
    }
</style>