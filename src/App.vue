<script >
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import { store } from "./store.js";
export default {
  data(){
    return{
      store
    };
  },
  components: {
    AppHeader,
  }
};


</script>

<template>
<AppHeader />
  
</template>

<style lang="scss">
@use "./style/general.scss";

</style>
