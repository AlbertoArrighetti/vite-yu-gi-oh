<script>
export default {
    name: 'CardItem',

    props: {
        card: Object,
    },
    
    data() {
        return {

        }
    },
}
</script>

<template>
    <li class="card">
        <img :src="card.card_images[0].image_url" alt="card.name">
        <div class="name">{{ card.name }}</div>
        <div class="type">{{ card.archetype }}</div>
    </li>
</template>

<style lang="scss">
@use '../styles/variables' as *;

.card {
    display: flex;
    flex-flow: column;
    gap: 30px;

    width: calc(100% / 5 - $cardListGap / 5 * 4);

    text-align: center;
    background-color: $primaryColor;

    .name {
        color: white;
        text-transform: uppercase;
        font-weight: bold;
        padding: 0 10px;
    }
    .type {
        margin-bottom: 30px;
    }
}
</style>