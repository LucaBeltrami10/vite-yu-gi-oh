<template>
    <main>
        <div class="my_dropdown-menu">
            <select @change="$emite('selectedArchetype')" class="form-select mt-3" aria-label="Default select example">
                <option selected value="all">Select Archetype</option>
                <option v-for="(archetype) in archetypesList" :value="archetype.archetype_name">{{
                    archetype.archetype_name }}
                </option>
            </select>
        </div>
        <div class="my_container d-flex flex-wrap">
            <div class="w-100">
                <p class="upper-main px-4 py-2 m-0">Found {{ listCard.length }} Cards</p>
            </div>
            <CardElement class="my_element" v-for="card in listCard" :key="card.id" :name="card.name" :type="card.type"
                :frameType="card.frameType" :desc="card.desc" :imageSrc="card.card_images[0].image_url"
                :archetype="card.archetype" />
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
        'archetypesList',
    ],
    data() {
        return {

        }
    },
    methods: {
        selectedArchetype() {
            console.log('archetipo cambiato')
        }

    }

}
</script>
<style lang="scss">
@use '../style/partials/mixins' as *;
@use '../style/partials/variables' as *;

main {
    background-color: $background-main;
    width: 100%;
    padding: 1rem;

    div.my_dropdown-menu {
        margin-left: 12rem;
        width: 170px;
    }


    div.my_container {
        width: 70%;
        background-color: white;
        padding: 1.5rem 3rem;

        p.upper-main {
            color: white;
            font-weight: 700;
            font-size: 0.8rem;
            background-color: $background-color-upper-main;
        }

        .my_element {
            width: calc((100% / 4) - 18px);
            margin: 9px 9px;
        }

    }
}
</style>