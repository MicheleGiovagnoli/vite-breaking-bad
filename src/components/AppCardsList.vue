<script>
import AppCards from './AppCards.vue';
import AppCounter from './AppCounter.vue';

//Importo la variabile 'store' dal file store.js
import { store } from '../store.js';

export default {
    components: {
        AppCards,
        AppCounter,
    },
    nome: "AppCardsList",
    data() {
        return {
            store
        }
    },
};
</script>

<template>
    <div class="container">
        <AppCounter />
        <div class="row">
            <AppCards v-for="(element, i) in store.variabileDiProva.data" :key="i" :name="element.name"
                :images="element.card_images[0].image_url_small" :archetype="element.archetype" />
        </div>
    </div>
</template>

<style lang="scss">
.container {
    background-color: white;
    width: 80%;
    margin: 50px auto;
    padding: 40px;

    .row {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
    }

}
</style>