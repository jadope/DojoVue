<template>
<v-app>

<Toolbar/>
<v-main>
      <Search v-on:searchResults="searchResult"/>
      <ImageList v-bind:items="items"/>
</v-main>
<h1>Funciona</h1>
</v-app>
</template>

<script>

import Toolbar from './components/Toolbar.vue';
import Search from "./components/Search";
import ImageList from "./components/ImageList";


export default {
  name: 'App',

  components: {
    Toolbar,
    Search,
    ImageList
  },

  methods: {
    searchResult(response){
      this.items = response;
      console.log(this.items)
    }
  },

  data: () => ({
    items: [],
  }),
};
</script>
