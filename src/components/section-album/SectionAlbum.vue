<template>
    <section>
        <div v-if="albums.length > 0" class="container">
            <div class="container">
                <AlbumCard v-for="(album, i) in albumFiltered" :key="i" :album="album"></AlbumCard>

            </div>

        </div>

        <div v-else-if="albums.length === 0 && !albumsFound" class="noAlbumsFound">
            <h1>Nessun album trovato</h1>
        </div>

        <BaseLoader v-else></BaseLoader>

    </section>

</template>

<script>
import AlbumCard from '../album-card/AlbumCard.vue';
import axios from 'axios';
import BaseLoader from '../loader/BaseLoader.vue';

export default {
    name: "SectionAlbum",
    components: { AlbumCard, BaseLoader },
    data() {
        return {
            albums: [],
            albumsFound: true,

        }
    },
    props: {
        genre: String
    },
    methods: {

    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(resp => {
                this.albums = resp.data.response;
                console.log(this.albums);
                // this.albums[0].poster = "";
                this.albumsFound = this.albums.length > 0 ? true : false;

            })
    },
    computed: {
        albumFiltered() {
            return this.albums.filter(album => album.genre.toLowerCase().includes(this.genre))
        }

    },


}
</script>

<style scoped>
.noAlbumsFound {
    text-align: center;
    font-size: 25px;
    color: white;
}

.container {
    padding: 30px;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 15px 30px;
}
</style>