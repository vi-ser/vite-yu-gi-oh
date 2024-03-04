<script>
import axios from 'axios';
import { store } from './store.js'
import CardList from './components/CardList.vue'
import AppLogo from './components/AppLogo.vue'

export default {

  components: {
   CardList,
   AppLogo,
  },

  data() {
    return {
      cards: [],
      store,
    }
  },

  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=40&offset=0').then(res => {
      this.store.cards = res.data.data;
      // console.log(res)
    })
  }
}
</script>

<template>
  <AppLogo></AppLogo>
  <CardList></CardList>
</template>       

<style lang="scss">
@use './styles/general' as *;
@use './styles/variables' as *;


</style>
