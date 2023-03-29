<script>
import AppHeader from './components/AppHeader.vue';
import AppCardsList from './components/AppCardsList.vue';

import { store } from './store.js';

import axios from 'axios';

export default {
  components: {
    AppHeader,
    AppCardsList,
  },
  data() {
    return {
      store
    }
  },
  created() {
    axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=Alien')
      .then((response) => {
        this.store.variabileDiProva = response.data;
        console.log(response.data);
      })
  }
}
</script>

<template>
  <div class="wrapper">
    <AppHeader />
    <AppCardsList />
  </div>
</template>

<style lang="scss">
@use './styles/general.scss';

.wrapper {
  background-color: orange;
}
</style>
