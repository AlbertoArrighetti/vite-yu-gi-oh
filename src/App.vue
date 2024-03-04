<script>
// import axios
import axios from 'axios';
// store
import { store } from './store.js';

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
        console.log(res.data.data)
      })
    
  },
  components: {
  
  },

}
</script>

<template>
  
</template>

<style lang="scss">

</style>
