<template>
  <div class="col-7">
    <Spinner v-if="loading" />
    <div v-else>
      <div class="d-flex flex-column align-items-center justify-content-center">
        <img :src="country.flagImg" alt="country flag" style="width: 300px">
        <h1>{{ country.name }}</h1>
      </div>
      <table class="table">
        <thead />
        <tbody>
          <tr v-if="country.capital">
            <td style="width: 30%">
              Capital
            </td>
            <td>{{ country.capital }}</td>
          </tr>
          <tr v-if="country.area">
            <td>Area</td>
            <td>
              {{ country.area }} km<sup>2</sup>
            </td>
          </tr>
          <tr v-if="country.borders.length">
            <td>Borders</td>
            <td>
              <ul v-for="border in country.borders" :key="border">
                <li>
                  <router-link :to="`/details/${border}`">
                    {{ border }}
                  </router-link>
                </li>
              </ul>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
import Spinner from './SpinnerComponent.vue';

export default {
  name: 'CountryDetailComponent',
  components: {
    Spinner,
  },
  beforeRouteUpdate(to) {
    this.updatePage(to);
  },
  beforeRouteLeave() {
    this.loading = true;
  },
  data() {
    return {
      countryAlphaCode: '',
      country: {},
      loading: true,
    };
  },
  mounted() {
    this.updatePage(this.$route);
  },
  methods: {
    updatePage(route) {
      this.countryAlphaCode = route.params.country;
      this.fetchCountry(this.countryAlphaCode);
    },
    async fetchCountry(countryAlphaCode) {
      const response = await this.axios.get(`https://ih-countries-api.herokuapp.com/countries/${countryAlphaCode}`);
      const { data } = response;

      this.country = {
        name: data.name.official,
        capital: data.capital?.[0] || 'Capital not found',
        area: data.area,
        borders: data.borders,
        flagImg: `https://flagpedia.net/data/flags/icon/72x54/${data.alpha2Code.toLowerCase()}.png`,
      };
      this.loading = false;
    },
  },
};
</script>
