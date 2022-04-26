<template>
    <div class="col">
        <div class="card m-3 p-2 overflow-auto">
            <span class="card-title">Titolo: {{series.name}}</span>
            <span class="card-title">Titolo originale: {{series.original_name}}</span>
            <div class="d-flex justify-content-center">
                <span>Lingua:</span>
                <span class="bandiera ms-2" :class="(series.original_language == 'en') ? 'band-en' : (series.original_language == 'it') ? 'band-it' : 'band-altro'"></span>
            </div>
            <p class="card-text">Voto: {{series.vote_average}}</p>
        </div>
    </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
    name: 'SeriesCard',
    props: {
        series: Object
    },
    components: {
    // HelloWorld
    }
}
</script>

<style scoped lang="scss">
    .card {
        height: 250px;

        .bandiera {
            height: 25px;
            width: 25px;
            background-size: contain;
        } 

        .band-en {
            background-image: url('../assets/icons8-gran-bretagna-40.png');
        }

        .band-it {
            background-image: url('../assets/icons8-italia-40.png');
        }

        .band-altro {
            background-image: url('../assets/icons8-marocco-40.png');
        }
    }
</style>