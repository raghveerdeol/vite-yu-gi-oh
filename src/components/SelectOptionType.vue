<script>
export default {
data() {
return {

}
},
props: {
    archeType: {
        type: Object,
        required: true,
    }
}
}
</script>

<template>
            <option :value="archeType.archetype_name">
                {{ archeType.archetype_name }}
            </option>
</template>

<style scoped>

</style>