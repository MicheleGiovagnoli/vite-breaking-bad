<script>
export default {
    nome: "AppCards",
    props: {
        name: String,
        images: String,
        archetype: String,
    }
};
</script>

<template>
    <div>
        <img :src="images" :alt="images">
        <h1>{{ name }}</h1>
        <h2>{{ archetype }}</h2>
    </div>
</template>

<style lang="scss"></style>