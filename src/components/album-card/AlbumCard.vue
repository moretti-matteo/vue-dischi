<template>
    <div class="card">
        <div class="img__album">
            <img :src="album.poster" alt="">
        </div>
        <h2>{{ album.title }}</h2>
        <h4>{{ album.author }}</h4>
        <h5>{{ album.year }}</h5>
    </div>
</template>

<script>
export default {
    name: "AlbumCard",
    props: {
        album: Object
    },

}

</script>

<style lang="scss" scoped>
.card {
    padding: 20px;
    width: calc(100% / 5 - 30px);
    text-align: center;
    background-color: #2e3a46;

    & img {
        max-width: 100%;
    }

    h2 {
        color: white;
        margin: 10px 0 20px 0;
        overflow-wrap: break-word;
    }

    h4,
    h5 {
        color: grey;
        overflow-wrap: break-word;

    }
}

@media screen and (max-width: 992px) {
    .card {
        width: calc(100% / 3 - 30px);
    }
}

@media screen and (max-width: 600px) {
    .card {
        width: calc(100%  - 30px);
        
    }
}
</style>