<script>
export default {
    props: {
        card: Object,
    }
}
</script>

<template>
    <div class="card" >
        <div class="card-body">
            <img :src=" card.card_images[2].image_url" alt=""/>
            <h3 class="card-title"> {{ card.name }}</h3>
            <p class="card-text"> {{ card.archetype }}</p>
           
        </div>
    </div>

</template>

<style lang="scss" scoped>
</style>