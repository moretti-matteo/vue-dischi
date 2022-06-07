<template>
  <main>
      <SectionAlbum></SectionAlbum>
  </main>
</template>

<script>
import SectionAlbum from '../section-album/SectionAlbum.vue';
export default {
    name: "BaseMain",
    components: { SectionAlbum }
}
</script>

<style lang="scss">
main{
    height: 100%;
}
</style>