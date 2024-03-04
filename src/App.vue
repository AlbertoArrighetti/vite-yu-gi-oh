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
    
  },
  components: {
    CardList,
    AppPagination,
  },

}
</script>

<template>
    <AppPagination></AppPagination>
    <CardList></CardList>
</template>

<style lang="scss">

</style>
