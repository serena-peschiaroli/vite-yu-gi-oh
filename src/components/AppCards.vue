<script>
export default {
    props: {
        cards: Object,
    }
}
</script>

<template>
    <div class="card text-center mt-2" >
        
            <img :src="cards.card_images[0].image_url_small" alt=""/>
            <p class="text-white"> {{ cards.name }}</p>
            <p class="text-black"> 
                {{ cards.archetype ? cards.archetype : cards.type }}
            </p>
           
        
    </div>

</template>

<style lang="scss" scoped>
.card {
    background-color: orange;
}
</style>