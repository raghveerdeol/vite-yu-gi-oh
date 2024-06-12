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
    <div v-for="card in store.cardsList">{{ card.name }}</div>
    <MainSingleCard/>
</template>

<style scoped>

</style>