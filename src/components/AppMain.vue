<template>
    <main>
        <div class="my_container container-fluid">
            <div class="row">
                <CardElement class="col-3 p-3" v-for="card in listCard" :key="card.id" :name="card.name" :type="card.type"
                    :frameType="card.frameType" :desc="card.desc" :imageSrc="card.card_images[0].image_url"
                    :archetype="card.archetype" />
            </div>

        </div>
    </main>
</template>
<script>
import CardElement from './CardElement.vue';
export default {
    components: {
        CardElement,
    },
    props: [
        'listCard',
    ],

}
</script>
<style lang="scss">
@use '../style/partials/mixins' as *;
@use '../style/partials/variables' as *;

main {
    background-color: $background-main;
    width: 100%;
    padding: 1rem;

    div.my_container {
        width: 70%;
        background-color: white;
        padding: 3rem;

    }
}
</style>