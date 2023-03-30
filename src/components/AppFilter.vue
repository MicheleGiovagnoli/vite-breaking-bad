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
        <select name="filter" id="filter" v-model="store.filter" @change="$emit('doFilter')">
            <option value="">seleziona un'archetipo </option>
            <option :value="element" v-for="(element, i) in store.archetype" :key="i">{{ element }}
            </option>
        </select>
    </div>
</template>


<style lang="scss">
.filter-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 50px;

    #filter {
        padding: 10px;
        border-radius: 5px;
        border: none;
        transition: all 0.5s ease;

        &:hover {
            background-color: rgb(121, 117, 117);
        }
    }
}
</style>