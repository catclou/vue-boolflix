<template>
    <section class="container">
        <h3 class="lead text-light">Film:</h3>
        <div class="row row-cols-5">
            <CardComp v-for="(elem, index) in propsArrayFilms2" :key="index" :film="elem"/>
        </div>
    </section>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import CardComp from './CardComp.vue'


export default {
    name: 'FilmList',
    components: {
    // HelloWorld
    CardComp
    },
    props: {
        propsArrayFilms2: Array
    }
}
</script>

<style scoped lang="scss">
    
</style>