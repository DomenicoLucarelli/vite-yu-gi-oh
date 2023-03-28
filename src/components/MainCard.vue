<script>

export default {



    data() {
        return {

            isOn: false

        }
    },

    methods:{
        isMouseOn(){
            this.isOn = true
        }
    },
    props: {
        image: String,
        cardName: String,
        descrizione: String,
    }
}
</script>

<template>
    
    <div class="card " @mouseover="isMouseOn()" :style="this.isOn ?{display:'none'} :{display:'inline-block'}" >

        <div class="image">
            <img :src="image" alt="">
        </div>

        <div class="title">
            <span>{{ cardName }}</span>
        </div>

    </div>
    <div class="info" :style="this.isOn ?{display:'inline-block'} :{display:'none'}" @mouseleave="this.isOn = false">
        <h2>Description</h2>
        <p>{{ descrizione }}</p>
    </div>
</template>

<style lang="scss" scoped>
.info{
    width:calc(100% / 5 - 20px / 5 * 4) ;
    background-color: #403d39;
    height: 300px;
    display: none;
    overflow: auto;
    
    h2,p{
        text-align: center;
    }
    
}
.card {
    width: calc(100% / 5 - 20px / 5 * 4);

    .image {
        width: 100%;

        img {
            width: 100%;

        }
    }

    .title{
        text-align: center;
        background-color: #403d39;
        border-radius: 10px;
    }

}
</style>