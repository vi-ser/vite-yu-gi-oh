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
    <div class="card-info">

        <span id="card-name"> {{card.name}} </span>
        <small id="card-archetype"> {{card.type}} </small>
        
    </div>
</li>

</template>

<style lang="scss">
@use '../styles/general' as *;
@use '../styles/variables' as *;


li {
    width: calc(100% / 5 - $cardsGap / 5 * 4);
    background-color: rgba(255, 255, 255, 0.05);
    
    img {
        width: 100%;
    }
    .card-info {
        padding: 16px; 

        small {
            display: block;
            color: rgba(255, 255, 255, 0.4);
        }
    }
}
</style>