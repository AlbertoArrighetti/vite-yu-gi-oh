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

</template>

<style lang="scss">
@use '../styles/variables' as *;

.character {
    display: flex;
    flex-flow: column;
    gap: .7em;

    width: calc(100% / 5 - $characterListGap / 5 * 4);

    text-align: center;
}
</style>