<template>
    <section>
        <h3 class="lead">Questa è la film list</h3>
        <CardComp/>
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
    }
}
</script>

<style scoped lang="scss">
    section {
        border: 1px solid antiquewhite;

    h3 {
        color: maroon;
    }

    }
    
</style>