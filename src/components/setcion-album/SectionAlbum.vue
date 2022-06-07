<template>
    <section>
        <div v-if="albums.length > 0" class="container">
            <AlbumCard v-for="(album, i) in albums" :key="i" :album="album"></AlbumCard>
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
.container {
    padding: 30px;
    display: flex;
    flex-wrap: wrap;
    gap: 15px 30px;
}
</style>