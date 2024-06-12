<script>
export default {
data() {
return {

}
},
props: {
    singleCard: {
        type: Object,
        required: true,
    }
}
}
</script>

<template>
<div class="card col-3 border-5 border-light" style="width: 18rem;">
    <img :src="singleCard.card_images[0].image_url" class="card-img-top" alt="...">
    <div class="card-body">
        <h5 class="card-title">{{ singleCard.name }}</h5>
        <p class="card-text">{{ singleCard.archetype }}</p>
    </div>
</div>
</template>

<style scoped>

</style>