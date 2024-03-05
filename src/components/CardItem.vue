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
    <img class="front-card" :src="card.card_images[0].image_url" alt="">
    <img class="back-card" src="/img/back-card.jpg" alt="">
    <div class="card-info">

        <span id="card-name"> {{card.name}} </span>
        <small id="card-race"> {{card.race}} </small>
        
    </div>
</li>

</template>

<style lang="scss">
@use '../styles/general' as *;
@use '../styles/variables' as *;


li {
    width: calc(100% / 5 - $cardsGap / 5 * 4);
    background-color: rgba(255, 255, 255, 0.05);
    position: relative;
    overflow: hidden; 
    
    img {
        width: 100%;
        transition: transform 0.5s;
        transform-style: preserve-3d;    

        &:hover {
            transform: rotateY(180deg);
        }
    }

    .front-card {
        position: relative;
        backface-visibility: hidden;
    }

    .back-card {
        position: absolute;
        top: 0;
        left: 0;
        backface-visibility: hidden;
        transform: rotateY(180deg);
    }

    img:hover + .back-card {
        transform: rotateY(0deg);
    }

    img:hover {
        transform: rotateY(-180deg);
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
