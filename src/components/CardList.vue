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


            <select class="search" v-model="store.selectedArchetype" @change="$emit('search')">
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
                <div>
                    Total cards on database: {{ store.numberOfCard }}
                </div>
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

    .search {
        padding: 10px;
        margin: 10px 0;
        margin-right: 10px;

        font-size: 16px;
    }
    .founded {
        display: flex;
        justify-content: flex-end;

        padding: 28px 24px;
        margin-bottom: 10px;

        font-weight: bold;
        font-size: 14px;
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