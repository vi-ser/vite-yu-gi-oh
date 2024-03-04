<script>
import axios from 'axios';
import { store } from './store.js'
import CardList from './components/CardList.vue'

export default {

  components: {
   CardList,
  },

  data() {
    return {
      cards: [],
      store,
    }
  },

  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then(res => {
      this.store.cards = res.data.data;
      // console.log(res)
    })
  }
}
</script>

<template>
  <CardList>
  </CardList>
</template>       

<style lang="scss">
@use './styles/general.scss' as *;


</style>
