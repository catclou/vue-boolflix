<template>
    <section class="container pt-3">
        <h3 class="text-light">Serie tv:</h3>
        <div class="row row-cols-5">
            <SeriesCard v-for="(elem, index) in propsArraySerie2" :key="index" :series="elem"/>
        </div>
    </section>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import SeriesCard from './SeriesCard.vue'


export default {
    name: 'SeriesList',
    components: {
    // HelloWorld
    SeriesCard,
    },
    props: {
        propsArrayFilms2: Array,
        propsArraySerie2: Array,
    }
}
</script>

<style scoped lang="scss">
    
</style>