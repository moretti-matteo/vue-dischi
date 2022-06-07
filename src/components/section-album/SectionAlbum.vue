<template>
    <section>
        <div v-if="albums.length > 0" class="container">
            <AlbumCard v-for="(album, i) in albums" :key="i" :album="album"></AlbumCard>
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
            albumsFound: true

        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(resp => {
                this.albums = resp.data.response;
                console.log(this.albums);
                this.albums[0].poster = "";
                if (this.albums.length === 0) {
                    this.albumsFound = !this.albumsFound;
                }
            })
    }
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
    gap: 15px 30px;
}
</style>