<script>
import { store } from '../store.js';

export default {
    nome: "AppFilter",
    data() {
        return {
            store,
        }
    },
    methods: {
    },
}
</script>
<template>
    <div class="filter-container">
        <select name="filter" id="filter" v-model="store.filter">
            <option value="">seleziona un'archetipo </option>
            <option value="" v-for="(element, i) in store.archetype" :key="i" @click="$emit('doFilter')">{{ element }}
            </option>
        </select>
    </div>
</template>
<style lang="scss">
#filter {
    width: 100px;
}
</style>