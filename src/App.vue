<template>
  <div class="app">
    <Navbar />

    <div class="d-flex justify-content-center">
      <Spinner v-if="loading" />
      <div v-else className="container">
        <div className="row">
          <CountriesList :countries="countries" />
          <router-view />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Navbar from './components/NavbarComponent.vue';
import CountriesList from './components/CountriesListComponent.vue';
import Spinner from './components/SpinnerComponent.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    CountriesList,
    Spinner,
  },
  data() {
    return {
      countries: [],
      loading: true,
    };
  },
  mounted() {
    this.fetchCountries();
  },
  methods: {
    async fetchCountries() {
      const { data } = await this.axios.get('https://ih-countries-api.herokuapp.com/countries');

      const countries = [];
      data.forEach((country) => {
        const newCountry = {
          name: country.name.official,
          alphaCode: country.alpha3Code,
          flagImg: `https://flagpedia.net/data/flags/icon/72x54/${country.alpha2Code.toLowerCase()}.png`,
        };
        countries.push(newCountry);
      });
      // just asign all data at once to avoid unneeded reactivity
      this.countries = countries;
      this.loading = false;
    },
  },
};
</script>
