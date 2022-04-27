<template>
    <header class="bg-dark d-flex align-items-center justify-content-between">
        <h1 class="text-danger text-uppercase fw-bold ms-2">netflix dei poveri</h1>
        <form action="">
            <div class="d-flex m-2">
                <input type="text" v-model="testoCercato" @keydown.enter.prevent="$emit( 'ricerca', testoCercato )" class="me-2">
                <button @click.prevent="$emit( 'ricerca', testoCercato )" class="btn btn-outline-danger h-25">Cerca</button>
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

        height: 6vh;

        h1 {
            margin-bottom: 0!important;
        }

        input:focus {
            outline: red !important;
            border: 1.5px solid red;
            box-shadow: 0 0 5px red;
        }
    }
</style>