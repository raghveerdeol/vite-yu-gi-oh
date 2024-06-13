<script>
import { store } from '../store.js';
import SelectOptionType from './SelectOptionType.vue'

export default {
    components: {
        SelectOptionType,
    },
    data() {
    return {
        store,
    }
    }
}
</script>

<template>
    <div class="scelta">
        <select class="px-5 py-2 bg-light border-0 rounded-3">
            <SelectOptionType v-for="(type, index) in store.archeTypeList" :key="index" :arche-type="type"/>
        </select>
    </div>
</template>

<style lang="scss" scoped>
.scelta{
    margin: 0 auto;
    width: 75%;
    padding: 1rem 0;
}
</style>