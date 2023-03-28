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
    <div class="deck">

        <MainCard v-for="(card, index) in store.cards" :image="card.card_images[0].image_url" :card-name="card.name" >

        </MainCard>

       

    </div>
</template>

<style lang="scss" scoped>
.deck {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    
    

    
}
</style>