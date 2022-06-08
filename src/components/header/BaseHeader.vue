<template>
    <header>
        <div class="header__left">
            <div class="logo-container">
                <img src="../../assets/img/spotify-logo.png" alt="">
            </div>
        </div>
        <div class="header__right">
            <select name="genre" style="padding: 5px;" @change="$emit('search',value)" v-model="value">
                <option value="">All</option>
                <option value="rock">Rock</option>
                <option value="metal">Metal</option>
                <option value="jazz">Jazz</option>
                <option value="pop">Pop</option>
            </select>
        </div>
    </header>
</template>

<script>
export default {
    name: "BaseHeader",
    data() {
        return {
            value: ""
        }
    },
    methods: {}

}
</script>

<style lang="scss" scoped>
header {
    background: var(--header-color);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 5px 20px;
}

img {
    width: 80px;
    height: auto;
}
</style>