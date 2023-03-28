<script>


export default {

    name: 'MainCard',

    data() {
        return {



        }
    },

    props: {
        card: Object,
    }
}
</script>

<template>
    <div class="card">

        <div class="image">
            <img :src="imageUrl" alt="">
        </div>

        <div class="title">

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

}
</style>