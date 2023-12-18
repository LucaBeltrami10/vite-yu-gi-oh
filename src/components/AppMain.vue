<template>
    <main>
        <div class="my_container">
            <CardElement />

        </div>
    </main>
</template>
<script>
import CardElement from './CardElement.vue';
export default {
    components: {
        CardElement,
    }

}
</script>
<style lang="scss">
@use '../style/partials/mixins' as *;
@use '../style/partials/variables' as *;

main {
    background-color: $background-main;
    height: 500px;
    width: 100%;
    padding: 1rem;

    div.my_container {
        height: 400px;
        width: 70%;
        background-color: white;

    }
}
</style>