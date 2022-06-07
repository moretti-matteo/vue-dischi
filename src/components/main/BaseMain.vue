<template>
  <main>
      <SectionAlbum></SectionAlbum>
  </main>
</template>

<script>
import SectionAlbum from '../setcion-album/SectionAlbum.vue';
export default {
    name: "BaseMain",
    components: { SectionAlbum }
}
</script>

<style lang="scss" scoped>
main{
    background-color: var(--main-color);
    height: 100vh;
}
</style>