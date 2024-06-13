<script>
import MainSelect from './MainSelect.vue';
import MainCardList from './MainCardList.vue';
import MainLoader from './MainLoader.vue';
import axios from 'axios';
import { store } from '../store.js';

export default {
    components: {
        MainSelect,
        MainCardList,
        MainLoader,
    },
data() {
return {
        store,
        isLoading: false,
}
},
methods: {
    getCardsList(typeToSearch){
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0&archetype='+ typeToSearch)
        .then((response) => {
                // handle success
                console.log(response.data.data);
                this.store.cardsList = response.data.data;
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            .finally(function () {
                // always executed
            });
    },
    load2Sec(){
        setTimeout(() =>{
            this.isLoading = false;
        }, 2000)
    },
    getArchetype(){
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((response) => {
                // handle success
                console.log(response);
                this.store.archeTypeList = response.data;
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            })
            .finally(function () {
                // always executed
            });
    },
    searchCard(type){
        console.log("selected!!");
        console.log(type);
        this.getCardsList(type)
        this.isLoading = true;
        this.load2Sec();
    }
},
created(){
    this.getCardsList();
    this.getArchetype();
    // this.load2Sec();
}
}
</script>

<template>
    <main >
        <MainSelect @selected="searchCard"/>
        <MainCardList v-if="isLoading === false"/>
        <MainLoader v-else/>
    </main>
</template>

<style lang="scss" scoped>
    main{
        background-color: #d48f38;
    }
</style>