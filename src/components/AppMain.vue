<script>
import axios from 'axios';

import { store } from '../store.js';

import MainCard from './MainCard.vue';
import AppSearch from './AppSearch.vue';


export default {

    data() {
        return {
            store,
        };
    },

    created() {
        axios.get(this.store.ApiLink).then((res) => {

            this.store.cards = res.data.data
            
        })
    },

    methods:{
        search(){
            let newApi = this.store.ApiLink

            if(this.store.searcName != ''){
                newApi += this.store.ApiName + this.store.searcName
            }

            axios.get(newApi).then((res)=>{
                this.store.cards = res.data.data
            }).catch(()=>{
                alert('Errore: elemento non esistente')
            })
            
        }

    },

    components: { MainCard, AppSearch}
}
</script>

<template>

    <AppSearch @searchClick="search()"></AppSearch>

    

    <div class="deck" >

        <MainCard v-for="(card, index) in store.cards" :image="card.card_images[0].image_url" :card-name="card.name" :descrizione="card.desc">

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