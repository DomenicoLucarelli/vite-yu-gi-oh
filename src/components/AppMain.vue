<script>
import axios from 'axios';
import { store } from '../store.js';

import MainCard from './MainCard.vue';

export default {
    name: "AppMain",
    data() {
        return {
            store,
        };
    },

    created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0').then((res) => {

            this.store.cards = res.data.data

        })
    },

    components: { MainCard }
}
</script>

<template>
    <div class="deck">
        <MainCard v-for="(card, index) in this.store.cards" :image="card[index].card_images[0].image_url">

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