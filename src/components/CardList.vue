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


            <select v-model="store.selectedArchetype">
                <option disabled value="">Seleziona una</option>
                
                <option selected value="ShowAll">Mostra Tutte</option>

                <option 
                v-for="currentArchetype in store.archetype"    
                :value="currentArchetype.archetype_name"
                >
                {{ currentArchetype.archetype_name }}
                </option>
            </select>
        
            
            <div class="founded">
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

    .founded {
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