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
            v-for="currentCard in store.card"
            :card="currentCard"
            ></CardItem>
        </ul>

    </div>
</template>

<style lang="scss">
</style>