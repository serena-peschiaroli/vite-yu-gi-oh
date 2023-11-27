<script>
import { store } from '../store';
import AppCards from './AppCards.vue';
export default {
    components: { AppCards},
};

</script>

<template>
    <div class="ms_container">
        <div class="row">
            <div class="col" v-for="card in store.data" :key="card.id">
                <AppCards :card="card" />

            </div>
        </div>
    </div>

</template>

<style lang="scss" scoped>
.ms_container {
    width: 90%;
    margin: 0 auto;
}
</style>