<template>
  <h1 class="text-center">Ciao</h1>
  <i class="fa fa-solid fa-home"></i>
</template>

<script>
  import axios from 'axios';
  import { store } from './store.js';
  export default {
    name: 'App',
    components: {
    
  },
  data() {
    return {
      store,
      days: [],
      travels: [],
    }
  },
  methods: {
    getDays() {
            axios.get(this.store.apiBaseUrl + '/days').then((res) => {
                this.days = res.data.results;
            });
        },
        getTravels() {
          axios.get(this.store.apiBaseUrl + '/travels').then((res) => {
                this.travels = res.data.results;
            });
        }
  },
  mounted() {
    this.getDays();
    this.getTravels();
  }
  }  
</script>

<style lang="scss" scoped>

</style>