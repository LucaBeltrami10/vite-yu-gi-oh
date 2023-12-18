<template>
    <header>
        <img class="ms-4" src="https://upload.wikimedia.org/wikipedia/commons/2/21/Yu-Gi-Oh%21.png" alt="yu-gi-oh logo">
        <h1 class="ms-4">Yu-Gi-Oh Api</h1>
    </header>
</template>
<script>
export default {

}
</script>
<style lang="scss" scoped>
@use '../style/partials/mixins' as *;
@use '../style/partials/variables' as *;

header {
    @include flex(row, start, center);
    height: 80px;

    img {
        height: 100%;
    }
}
</style>