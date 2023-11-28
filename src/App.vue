<script >
import { store } from "./store.js"
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppCardsList from "./components/AppCardsList.vue";
import CardSelector from "./components/CardSelector.vue";

export default {
  created(){
    this.store.loading = true;
    axios.get(this.store.apiUrl).then((resp) => {
      this.store.cards = resp.data.data;
      this.store.loading = false;
      console.log('Cards Data:', this.store.cards);
    });
  },
  data(){
    return{
      store,
      selectedArchetype: '',
      cardsCount: store.cardsCount,
    };
  },
  components: {
    AppHeader,
    AppCardsList,
    CardSelector,
},
  methods : {
    handleFilterChange(selectedArchetype) {
      //aggiorna gli archetipy in prop data
      this.selectedArchetype = selectedArchetype;
      //prende e aggiorna le carte in base alla selezione
      this.store.loading = true;
      axios.get(this.store.apiUrl + `&archetype=${selectedArchetype}`).then((resp) => {
        this.store.cards = resp.data.data;
        this.store.loading = false;
        console.log ('Cards data: ', this.store.cards);
        // aggiorna il conteggio delle carte
        this.cardsCount = store.cards.length;
      });
    },
  },
};


</script>

<template>
<AppHeader />
<CardSelector @filter-change="handleFilterChange"  :cardsCount="cardsCount" />
<AppCardsList />
  
</template>

<style lang="scss">
@use "./style/general.scss";

</style>
