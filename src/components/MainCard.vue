<script>

export default {



    data() {
        return {



        }
    },

    props: {
        image: String,
        cardName: String,
    }
}
</script>

<template>
    <div class="card">

        <div class="image">
            <img :src="image" alt="">
        </div>

        <div class="title">
            <span>{{ cardName }}</span>
        </div>

    </div>
</template>

<style lang="scss" scoped>
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