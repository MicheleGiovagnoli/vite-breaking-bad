<script>
import { store } from '../store.js';
export default {
    nome: "AppCounter",
    data() {
        return {
            store
        }
    },
    computed: {
        message() {
            return `ci sono ${this.store.variabileDiProva.data.length} risultati`;
        }
    }
}
</script>

<template>
    <div class="container-AppCounter">
        <h4 v-if="this.store.variabileDiProva.data.length > 0">{{ message }}</h4>
        <h4 v-else>Nessun risultato</h4>
    </div>
</template>

<style lang="scss">
.container-AppCounter {
    width: 100px;
    height: 100px;
}
</style>