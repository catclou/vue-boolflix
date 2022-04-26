<template>
    <div class="col">
        <div class="card m-3">
            <span class="card-title">Titolo: {{film.title}}</span>
            <span class="card-title">Titolo originale: {{film.original_title}}</span>
            <span>Lingua: {{film.original_language}}</span>
            <p class="card-text">Voto: {{film.vote_average}}</p>
        </div>
    </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
    name: 'CardComp',
    props: {
        film: Object
    },
    components: {
    // HelloWorld
    }
}
</script>

<style scoped lang="scss">
    h5 {
        color: greenyellow;
    }
</style>