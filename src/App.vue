<script>
import axios from 'axios';
import { store } from './store.js'
import CardList from './components/CardList.vue'
import AppLogo from './components/AppLogo.vue'
import CardSearch from './components/CardSearch.vue';

export default {

  components: {
   CardList,
   AppLogo,
   CardSearch,
  },

  data() {
    return {
      // flag di caricamento
      loading: true,
      store,
    }
  },

  methods: {

  searchArchetype() {

    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=' + this.store.selectItem)
     .then(res => {
        console.log(res.data)

        this.store.cards = res.data.data;
        this.store.totalCards = res.data.data.length;
      });

     console.log("Ricerca percepita")
  },

},

  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=800&offset=1275').then(res => {
      this.store.cards = res.data.data;
      // mostro le carte totali
      this.store.totalCards = res.data.meta.total_rows;
      // imposto il flag su false
      this.loading = false; 
    })
  }
}
</script>

<template>


    <div v-if="loading" class="loader">
      <div class="logo-loader">
        <img id="logo" src="/img/logo.png" alt="logo yu-gi-oh">
        <span id="text-loading">caricamento</span>
      </div>
    </div>

    <AppLogo v-if="!loading"></AppLogo>
    <CardSearch v-if="!loading" @search="searchArchetype()"></CardSearch>
    <CardList v-if="!loading"></CardList>

</template>       

<style lang="scss">
@use './styles/general' as *;
@use './styles/variables' as *;

.logo-loader {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;

     #logo {
        max-width: 300px;
     }

     #text-loading {
      margin-top: 24px;
     }

}


</style>
