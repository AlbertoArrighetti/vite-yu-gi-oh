<script>
// import axios
import axios from 'axios';
// store
import { store } from './store.js';

// components
import CardList from './components/CardList.vue';
import AppPagination from './components/AppPagination.vue';


export default {
  data() {
    return {
      store,
    }
  },

  created() {

    axios
      .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then(res => {
        this.store.cards = res.data.data
      })

      axios
        .get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then(res => {
        this.store.archetype = res.data;
      })
    
  },
  components: {
    CardList,
    AppPagination,
  },

  methods: {
    searchArchetype() {
      if (this.store.selectedArchetype !== "ShowAll"){
        axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype=' + this.store.selectedArchetype)
        .then(res => {
          this.store.cards = res.data.data
        })
      }else {
        axios
        .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then(res => {
          this.store.cards = res.data.data
        })
      }
    }
  },

}
</script>

<template>
    <AppPagination></AppPagination>
    <CardList @search="searchArchetype()"></CardList>
</template>

<style lang="scss">

</style>
