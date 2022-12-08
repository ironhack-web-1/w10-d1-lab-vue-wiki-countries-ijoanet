<template>
  <div class="col-5" style="max-height: 90vh; overflow-y: scroll">
    <div v-for="country in countries" :key="country.alphaCode" class="list-group">
      <router-link class="list-group-item list-group-item-action" :to="`/details/${country.alphaCode}`">
        <img :src="country.flagImg">
        <p>{{ country.name }}</p>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CountriesListComponent',
  props: {
    countries: {
      type: Array,
      required: true,
    },
  },
};
</script>
