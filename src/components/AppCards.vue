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
    <div class="cards-container">
        <img :src="images" :alt="images">
        <h1>{{ name }}</h1>
        <h2>{{ archetype }}</h2>
    </div>
</template>

<style lang="scss">
.cards-container {
    width: calc((100% /5) - 20px);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 20px;

    h1 {
        font-size: 10px;

    }
}
</style>