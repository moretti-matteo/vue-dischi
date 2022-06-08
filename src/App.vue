<template>
  <div id="app">
    <BaseHeader @search="filterAlbums"></BaseHeader>
    <BaseMain :genre="genre">
    </BaseMain>
  </div>
</template>

<script>
import BaseHeader from './components/header/BaseHeader.vue';
import BaseMain from './components/main/BaseMain.vue';

export default {
  name: 'App',
  components: {
    BaseHeader,
    BaseMain
  },
  data(){
    return{
      genre:""
    }
  },
  methods: {

    filterAlbums(genre) {
      this.genre = genre;
    }

  }
}
</script>

<style lang="scss">
@import './assets/style/global.scss';

#app {}
</style>
