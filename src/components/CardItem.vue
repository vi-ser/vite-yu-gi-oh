<script>
export default {
    name: 'CardItem',

    props: {
        card: Object,
    }
}
</script>

<template>
<li>
    <img :src="card.card_images[0].image_url" alt="">
    <span id="card-name"> {{card.name}} </span>
    <!-- <span id="card-archetype"> {{card.archetype}} </span> -->
</li>

</template>

<style lang="scss">
@use '../styles/general.scss' as *;

li {
    width: calc(100% / 5);
    
    img {
        width: 100%;
    }
}
</style>