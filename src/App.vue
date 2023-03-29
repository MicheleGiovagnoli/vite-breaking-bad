<script>
import AppHeader from './components/AppHeader.vue';

import { store } from './store.js';

import axios from 'axios';

export default {
  components: {
    AppHeader,
  },
  data() {
    return store
  },
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Alien')
      .then((response) => {
        console.log(response.data.archetype);
      })
  }
}
</script>

<template>
  <AppHeader />
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
