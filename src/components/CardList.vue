<script>

import CardItem from './CardItem.vue';
import CardSearch from './CardSearch.vue';
import { store } from '../store.js';

export default {
    name: 'CardList',

    components: {
        CardItem,
        CardSearch,
    },

    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div class="container">

        <CardSearch></CardSearch>

        <div class="list-number">
            <strong id="search-result">Carte totali: {{ store.totalCards }}</strong>
        </div>

        <ul>
            <CardItem
            v-for="currentCard in store.cards"
            :card="currentCard"
            ></CardItem>
        </ul>

    </div>
</template>

<style lang="scss" scoped>
@use '../styles/general' as *;
@use '../styles/variables' as *;


.container {

    background-color: rgba(255, 255, 255, 0.05);

    #search-result {
        display: block;
        padding: 24px;
        background-color: rgba(255, 255, 255, 0.2);
        margin-bottom:calc(2 * $cardsGap );
    }

    ul {
        display: flex;
        gap: $cardsGap;

        flex-flow: wrap;
        list-style: none;

        text-align: center;
    }
}

</style>