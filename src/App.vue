<script >
import { store } from "./store.js";
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppCardsList from "./components/AppCardsList.vue";

export default {
  created(){
    this.store.loading = true;
    axios.get(this.store.apiUrl).then((resp) => {
      this.store.cards = resp.data.results;
      this.store.loading = false;
    });
  },
  data(){
    return{
      store
    };
  },
  components: {
    AppHeader,
    AppCardsList
    
  }
};


</script>

<template>
<AppHeader />
  
</template>

<style lang="scss">
@use "./style/general.scss";

</style>
