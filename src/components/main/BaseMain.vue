<template>
    <main>
        <SectionAlbum :genre="genre"></SectionAlbum>
    </main>
</template>

<script>
import SectionAlbum from '../section-album/SectionAlbum.vue';
export default {
    name: "BaseMain",
    components: { SectionAlbum },
    props:{
        genre:String
    },
    
}
</script>

<style lang="scss">
main {
    height: 100%;
}
</style>