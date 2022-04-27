<template>
    <div class="col">

        <div class="flip-box">
            <div class="flip-box-inner">
                <div class="flip-box-front">
                    <img :src="`https://image.tmdb.org/t/p/w200/${film.poster_path}`">
                </div>
                <div class="flip-box-back overflow-auto">
                    <div class="m-3 p-2">
                        <span class="card-title d-inline-block lead fw-bold">{{film.title}}</span>
                        <span class="card-title d-block">Titolo originale: {{film.original_title}}</span>
                        <div class="d-flex justify-content-center">
                            <span>Lingua:</span>
                            <span class="bandiera ms-2" :class="(film.original_language == 'en') ? 'band-en' : (film.original_language == 'it') ? 'band-it' : 'band-altro'"></span>
                        </div>
                        <p class="card-text">Voto: {{film.vote_average}}
                            <i v-for="i in 5" :key="i" class="fa-star" :class="( i <= ratingStars() ) ? 'fa-solid' : 'fa-regular'"></i>
                        </p>
                        <p class="card-text"><span class="fw-bold">Trama: </span>{{film.overview}}</p>
                    </div>
                </div>
            </div>
        </div>

    </div>
</template>

<script>

export default {
    name: 'CardComp',
    props: {
        film: Object
    },
    methods: {
        ratingStars() {
            let ratingOnFiveScale = Math.ceil(this.film.vote_average)
            return ratingOnFiveScale / 2
        }
    }
}
</script>

<style scoped lang="scss">
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

img {
    width: 100%;
    height: 100%;
}

    /* The flip box container - set the width and height to whatever you want. We have added the border property to demonstrate that the flip itself goes out of the box on hover (remove perspective if you don't want the 3D effect */
.flip-box {
    background-color: transparent;
    width: 250px;
    height: 300px;
    perspective: 1000px; /* Remove this if you don't want the 3D effect */
    margin-bottom: 10px;
}

/* This container is needed to position the front and back side */
.flip-box-inner {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.8s;
    transform-style: preserve-3d;
}

/* Do an horizontal flip when you move the mouse over the flip box container */
.flip-box:hover .flip-box-inner {
    transform: rotateY(180deg);
}

/* Position the front and back side */
.flip-box-front, .flip-box-back {
    position: absolute;
    width: 100%;
    height: 100%;
    -webkit-backface-visibility: hidden; /* Safari */
    backface-visibility: hidden;
}

/* Style the front side (fallback if image is missing) */
.flip-box-front {
    background-color: #bbb;
    color: black;
}

/* Style the back side */
.flip-box-back {
    background-color: black;
    color: white;
    transform: rotateY(180deg);
}
</style>