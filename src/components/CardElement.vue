<template lang="">
    <div class="my_card card border border-0 rounded-0">
        <img :src="imageSrc">
        <div class="card-body">
            <p class="name">{{name}}</p>
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

div.my_card {
    background-color: $background-card;

    p.name {
        color: white;
        font-size: 0.9rem;
        font-weight: 700;
    }

}
</style>