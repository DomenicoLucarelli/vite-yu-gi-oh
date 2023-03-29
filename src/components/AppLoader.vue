<script>
export default {

    name:'AppLoader',

    data() {
        return {
            
        }
    },
}
</script>

<template>
    <div class="loader">
        Loading...
    </div>
</template>

<style lang="scss" scoped>

.loader{
    color: white;
    font-size: 30px;
    width: 100%;
    height: 100%;
    background-color: black;

    position: fixed;
    top: 0;
    left: 0;

    display: flex;
    justify-content: center;
    align-items: center;
}
    
</style>