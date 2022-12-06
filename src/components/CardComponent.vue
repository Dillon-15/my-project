<template>
    <div class="card" style="width: 18rem;">
        <img :src=imgPath class="card-img-top" alt="...">
        <div class="card-body">
            <h5 class="card-title">{{amovie.name}}</h5>
            <p class="card-text">{{amovie.overview}}</p>
            <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
    </div>
</template>

<script>
    export default({
        name: 'CardComponent',
        props:['amovie'],
        data(){
            return {
                imgPath: "https://image.tmdb.org/t/p/w500/" + this.amovie.poster_path
            }
        }
    })
</script>