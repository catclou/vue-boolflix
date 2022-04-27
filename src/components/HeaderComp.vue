<template>
    <header class="bg-dark d-flex align-items-center justify-content-between">
        <h1 class="text-danger text-uppercase fw-bold ms-2">netflix dei poveri</h1>
        <form action="">
            <div class="d-flex me-2">
                <label class="text-secondary me-2">Ricerca film e serie</label>
                <input type="text" v-model="testoCercato" @keydown.enter.prevent="$emit( 'ricerca', testoCercato )" class="me-2">
                <button @click.prevent="$emit( 'ricerca', testoCercato )">Cerca</button>
            </div>
        </form>
    </header>
</template>

<script>

export default {
    name: 'HeaderComp',
    data() {
        return {
            testoCercato: ''
        };
    },
    components: {
    // HelloWorld
    }
}
</script>

<style scoped lang="scss">
    header {

        h1 {
            margin-bottom: 0!important;
        }
    }
</style>