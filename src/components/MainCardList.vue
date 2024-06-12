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
    <div class="w-100 d-flex flex-wrap border-5 m-5">
        <MainSingleCard v-for="(card, index) in store.cardsList" :key="index" :single-card="card"/>
    </div>
</template>

<style scoped>

</style>