<script>
import { store } from '../store';
import AppCards from './AppCards.vue';
import AppLoader from './AppLoader.vue';


export default {
    data() {
        return {
            store
        };
    },
    components: { AppCards, AppLoader},
};

</script>

<template>
    <div class="ms_container mt-4">
        <AppLoader v-if="store.loading || store.cards.length < 20" />
        <div  v-else class="row align-items-stretch gx-2 gy-2">
            <div class="col" v-for="card in store.cards" :key="card.id">
                <AppCards :cards="card" />

            </div>
        </div>
    </div>

</template>

<style lang="scss" scoped>
.ms_container {
    width: 90%;
    margin: 0 auto;
    padding: 2rem;
    height: 100%;
    background-color: white;
}


</style>