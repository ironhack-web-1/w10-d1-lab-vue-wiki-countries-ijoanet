<template>
  <div className="app">
    <Navbar />
    <CountriesList />
    <div />
  </div>
</template>

<script>
import Navbar from './components/NavbarComponent.vue';
import CountriesList from './components/CountriesListComponent.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    CountriesList,
  },
};
</script>

<style>
</style>
