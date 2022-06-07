<template>
  <header>
      <div class="logo-container">
          <img src="../../assets/img/spotify-logo.png" alt="">
      </div>
  </header>
</template>

<script>
export default {
    name:"BaseHeader"
}
</script>

<style lang="scss" scoped>

header{
    border:1px solid;
    background: var(--header-color);
    
}

img{
    width: 80px;
    height: auto;
}



</style>