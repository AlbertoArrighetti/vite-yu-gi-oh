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
    <main>
        <div class="ext_container">
        
            
            <div class="counter">
                Found {{ store.cards.length }} cards
            </div>
            <ul>
                <CardItem 
                v-for="currentCard in store.cards"
                :card="currentCard"
                ></CardItem>
                
            </ul>
        </div>
    </main>

</template>

<style lang="scss">
@use '../styles/variables' as *;

.ext_container {
    padding: 70px;
    margin-bottom: 50px;

    .counter {
        padding: 28px 24px;

        font-weight: bold;
        color: white;
        background-color: #212529;
    }

    ul {
        list-style-type: none;
    
        display: flex;
        flex-flow: row wrap;
        
        gap:24px $cardListGap;
    }
}

</style>