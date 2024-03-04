<script>
import CardItem from './CardItem.vue';
// store
import { store } from '../store.js';

export default {
    name: 'CardList',

    components: {
        CardItem,
    },

    data() {
        return {
            store,
        }
    },
}
</script>

<template>
<div class="ext_container">
    <ul>
        <CardItem 
        v-for="currentCard in store.cards"
        :card="currentCard"
        ></CardItem>
        
    </ul>
</div>

</template>

<style lang="scss">
@use '../styles/variables' as *;

ul {
    list-style-type: none;

    display: flex;
    flex-flow: row wrap;
    
    gap:24px $cardListGap;
    padding: 70px;
}

</style>