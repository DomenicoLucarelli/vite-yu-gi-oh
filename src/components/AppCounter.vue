<script>

import {store} from '../store.js'

export default {

    name: 'AppCounter',

    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <div class="container">
        
        Il tuo deck è composto da {{ store.cards.length }} carte

    </div>
</template>

<style lang="scss" scoped>
    .container{
        width: 80%;
        font-size: 2em;
        font-weight: bold;
        text-align: center;
        
        
        
        
    }
</style>