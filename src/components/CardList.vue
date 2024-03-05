<script>
import CardItem from './CardItem.vue';
// store
import { store } from '../store.js';
// import axios
import axios from 'axios';

export default {
    name: 'CardList',

    components: {
        CardItem,
    },

    data() {
        return {
            store,

            archetype: [],
        }
    },

    created() {
        axios
      .get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then(res => {
        this.archetype = res.data;
      })
    },
}
</script>

<template>
    <main>
        <div class="ext_container">


            <select name="archetypes">
                <option 
                v-for="(selectedArchetype, index) in archetype"    
                value="">
                {{ selectedArchetype.archetype_name }}
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