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
    <div class="container">
        
        <ul>
            <li v-for="currentCard in store.cards">
                {{ currentCard.name }}
            </li>
        </ul>
    </div>
</div>

</template>

<style lang="scss">
@use '../styles/variables' as *;


</style>