<template>
    <section class="container pt-3">
        <h3 id="titolo_none" class="text-light">Film:</h3>
        <div class="row row-cols-5">
            <CardComp v-for="(elem, index) in propsArrayFilms2" :key="index" :film="elem"/>
        </div>
    </section>
</template>

<script>
import CardComp from './CardComp.vue'

export default {
    name: 'FilmList',
    components: {
        CardComp,
    },
    props: {
        propsArrayFilms2: Array,
    }
}
</script>

<style scoped lang="scss">

</style>