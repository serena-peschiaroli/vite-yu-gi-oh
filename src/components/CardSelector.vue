<script>
export default {
    // props per conteggio  carte
    props : {
        cardsCount : {
            type: Number,
            default: 0,
        },
        //prop per ricevere filtro 
        currentFilter: {
            type: String,
            defaul: '',
        },
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
        //methods x gestire cambio nel filtro corrente 
        methods: {
            handleCurrentFilterChange(newfilter) {
                //if conteggio solo se il filtro corrente coincide con l'archetipo
                this.$emit("aggiorno il numero di carte", this.cardsCount);
            }
        },
        //aggiungo un hook x chiamare il metodo quando il componente è creato
        created() {
            this.handleCurrentFilterChange(this.currentFilter);
        },

    },
};
</script>

<template>
    <section class="d-flex justify-between">

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