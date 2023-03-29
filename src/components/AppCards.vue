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
        <div class="description">
            <h1>{{ name }}</h1>
            <h2>{{ archetype }}</h2>
        </div>
    </div>
</template>

<style lang="scss">
.cards-container {
    width: calc((100% /5) - 10px);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    margin: 10px 0px;

    img {
        width: 100%;

    }

    .description {
        width: 100%;
        background-color: orange;
        height: 50px;
        text-align: center;

        h1 {
            font-size: 15px;
            color: white;
        }

        h2 {
            font-size: 10px;
        }
    }
}
</style>