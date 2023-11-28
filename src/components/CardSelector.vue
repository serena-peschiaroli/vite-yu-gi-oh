<script>
export default {
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
    <div>
        <label for="archetype">Select Archetype:</label>
        <select v-model="selectedArchetype">
        <option v-for="archetype in archetypes" :key="archetype" :value="archetype">
            {{ archetype }}
        </option>
    </select>
    <button class="btn btn-primary" @click="emitFilterEvent"> Filtra </button>
    </div>

</template>

<style scoped lang="scss">
</style>