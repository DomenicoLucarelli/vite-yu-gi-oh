<script>
import { store } from '../store.js';
export default {

    name: "AppSearch",

    data() {
        return {
            
            store,

        }
    },
}
</script>

<template>
    <div class="search">
        
        <input v-model="store.searcName" type="text" placeholder="inserisci archetipo">
        <button @click="$emit('searchClick')">Search</button>

    </div>
</template>

<style lang="scss" scoped>
    
    .search{
        display: flex;
        justify-content: center;
        gap: 5px;

        padding: 10px 0;
        margin-bottom: 10px;

        input{
            padding: 5px;
            border-radius: 5px;
            border: none;

        }

        button{
            cursor: pointer;
            padding: 5px 10px;
            border-radius: 5px;
            font-weight: bold;

        }
    }

</style>