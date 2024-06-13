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
        typeElement: "",
    }
    }
}
</script>

<template>
    <div class="scelta">
        <select class="px-5 py-2 bg-light border-0 rounded-3" name="card-type" v-model="typeElement">
            <option v-for="(type, index) in store.archeTypeList" :key="index"
            :value="type.archetype_name" @click="$emit('selected', typeElement)">
                {{ type.archetype_name }}
            </option>
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