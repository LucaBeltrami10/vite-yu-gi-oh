<template lang="">
    <div class="card">
        <img :src="imageSrc">
        <div class="card-body">
            <p class="card-text">{{name}}</p>
            <p>{{archetype}}</p>
        </div>
    </div>
</template>
<script>
export default {
    props: [
        'name',
        'type',
        'frameType',
        'desc',
        'imageSrc',
        'archetype',

    ]

}
</script>
<style lang="scss">
@use '../style/partials/mixins' as *;
@use '../style/partials/variables' as *;

div.card {}
</style>