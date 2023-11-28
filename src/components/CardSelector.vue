<script>
import { store } from "../store.js";

export default {
    props: {
        cardsCount: Number,

    },
    data() {
        return {
            selectedArchetype: '',
            archetypes: ["Alien", "Ally of Justice", "Ancient Gear"],
        };

    },
    methods: {
    
        emitFilterEvent() {
            //notifica componente genitore sull'archetipo selezionato
            this.$emit("filter-change", this.selectedArchetype);
        },

    },
};
</script>

<template>
    <section class="d-flex">

        <div class="input-container">
            <label for="archetype">Select Archetype:</label>
            <select v-model="selectedArchetype">
            <option v-for="archetype in archetypes" :key="archetype" :value="archetype">
                {{ archetype }}
            </option>
            </select>
            <button class="btn btn-primary" @click="emitFilterEvent"> Filtra </button>
        </div>

        <div class="count">
            {{ cardsCount }} carte trovate

        </div>
    </section>
</template>

<style scoped lang="scss">
@use "../style/general.scss";
.input-container {
    width: 40%;
    display: flex;
    align-items: center;
    gap: 1rem;

}







</style>