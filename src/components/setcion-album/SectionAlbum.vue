<template>
    <section class="container">
        <AlbumCard v-for="(album, i) in albums" :key="i" :album="album"></AlbumCard>
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


.container {
    padding-top: 30px;;
    display: flex;
    flex-wrap: wrap;
    gap:15px 30px;
}
</style>