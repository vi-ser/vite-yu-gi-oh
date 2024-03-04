<script>

import CardItem from './CardItem.vue';

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
    }
}
</script>

<template>
    <div class="container">

        <ul>
            <CardItem
            v-for="currentCard in store.cards"
            :card="currentCard"
            ></CardItem>
        </ul>

    </div>
</template>

<style lang="scss">
@use '../styles/general' as *;
@use '../styles/variables' as *;


.container {
    ul {
        display: flex;
        gap: $cardsGap;

        flex-flow: wrap;
        list-style: none;

        text-align: center;
    }
}

</style>