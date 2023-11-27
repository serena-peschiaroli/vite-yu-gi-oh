<script >
import { store } from "./store.js";
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import AppCardsList from "./components/AppCardsList.vue";

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
<AppCardsList />
  
</template>

<style lang="scss">
@use "./style/general.scss";

</style>
