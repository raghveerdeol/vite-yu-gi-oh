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
<div class="card border-5 border-light my-2">
    <img :src="singleCard.card_images[0].image_url" class="card-img-top" alt="...">
    <div class="card-body">
        <h5 class="card-title">{{ singleCard.name}}</h5>
        <p class="card-text">{{ singleCard.archetype }}</p>
    </div>
</div>
</template>

<style lang="scss" scoped>
    div.card{
        width: calc((100% / 5) - 1rem);
        background-color: #d48f38;
        &:hover{
            background-color: rgba(0, 0, 0, .5);
        }
    }
</style>