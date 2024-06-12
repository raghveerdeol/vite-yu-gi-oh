<script> 
import MainSingleCard from './MainSingleCard.vue';
import { store } from '../store.js';

export default {
    components: {
        MainSingleCard,
    },
data() {
return {
        store,
}
}
}
</script>

<template>
    <div class="d-flex flex-wrap border-5 justify-content-between">
        <MainSingleCard v-for="(card, index) in store.cardsList" :key="index" :single-card="card"/>
    </div>
</template>

<style lang="scss" scoped>
    div{
        background-color: white;
        width: 70%;
        margin: 0 auto;
    }
</style>