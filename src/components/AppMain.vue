<script>
import axios from 'axios';

import { store } from '../store.js';

import MainCard from './MainCard.vue';

export default {

    data() {
        return {
            store,
        };
    },

    created() {
        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0").then((res) => {

            this.store.cards = res.data.data
            
        })
    },

    components: { MainCard }
}
</script>

<template>
    <div class="loading" v-if="store.cards.length < 50">
        <strong>LOADING</strong>
    </div>

    <div class="deck" v-else="">

        <MainCard v-for="(card, index) in store.cards" :image="card.card_images[0].image_url" :card-name="card.name" >

        </MainCard>
    </div>
</template>

<style lang="scss" scoped>
.loading{
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 4em;
    color: red;

}
.deck {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    
    

    
}
</style>