<script>
import { store } from '../store';
import axios from 'axios';


export default {

  name: 'CardSearch',

  data() {
    return {
      store,
    }
  },

  created() {

    axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then(res => {
        console.log(res.data);
        this.store.archetypeList = res.data;
      });
  },

}




</script>

<template>
  <div class="dropdown-container">
    <div class="dropdown">
      <button class="btn btn-secondary dropdown-toggle rounded-0" type="button" data-bs-toggle="dropdown" aria-expanded="false">
        Seleziona Archetipo
      </button>
      <ul class="dropdown-menu rounded-0">
        <li v-for="archetype in store.archetypeList"><a class="dropdown-item" href="#">{{ archetype.archetype_name }}</a></li>
      </ul>
    </div> 
  </div> 
</template>

<style lang="scss">
@use '../styles/general' as *;
@use '../styles/variables' as *;

.dropdown-container {

  max-width: 1200px;
  margin: 0 auto !important;
  padding: 20px 60px !important;
  
  .btn {
    margin-bottom: $cardsGap;
    background-color: #595959;
    border: 1px solid #595959;

    &:hover {
      background-color: #a6a6a6;
      border: 1px solid #a6a6a6;
    }
  }
}

</style>