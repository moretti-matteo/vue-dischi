<template>
    <section>
        <div v-if="albums.length > 0" class="container">
            <AlbumCard v-for="(album, i) in albums" :key="i" :album="album"></AlbumCard>
        </div>
        <div v-else class="preload">
            <h1>Loading...</h1>
        </div>
    </section>

</template>

<script>
import AlbumCard from '../album-card/AlbumCard.vue';
import axios from 'axios';

export default {
    name: "SectionAlbum",
    components: { AlbumCard },
    data() {
        return {
            albums: []
        }
    },
    created() {
        axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then(resp => {
                this.albums = resp.data.response;
                console.log(this.albums);
            })
    }
}
</script>

<style scoped>
.preload {
    text-align: center;
    color:white;
    font-size: 25px;
    margin-top: 10px;
}

.container {
    padding: 30px;
    display: flex;
    flex-wrap: wrap;
    gap: 15px 30px;
}
</style>