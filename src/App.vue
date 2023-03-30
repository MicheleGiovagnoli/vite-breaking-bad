<script>
import AppHeader from './components/AppHeader.vue';
import AppCardsList from './components/AppCardsList.vue';
import AppFilter from './components/AppFilter.vue';

import { store } from './store.js';

import axios from 'axios';

export default {
  components: {
    AppHeader,
    AppCardsList,
    AppFilter,
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getArchetype() {
      let urlApi = 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0';
      if (this.store.filter) {
        urlApi += `&archetype=${store.filter}`;
        console.log(urlApi);
      }
      console.log(store.filter);
      axios.get(urlApi)
        .then((response) => {
          this.store.variabileDiProva = response.data;
          console.log(response.data);
        })
    }
  },
  created() {
    this.getArchetype();
  }
}
</script>

<template>
  <div class="wrapper">
    <AppHeader />
    <AppFilter @doFilter="getArchetype" />

    <AppCardsList />
  </div>
</template>

<style lang="scss">
@use './styles/general.scss';

.wrapper {
  background-color: orange;
}
</style>
