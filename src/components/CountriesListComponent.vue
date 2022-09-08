<template>
  <div class="container">
    <div class="row">
      <div class="col-5" style="max-height: 90vh; overflow: scroll">
        <div class="list-group">
          <router-link class="list-group-item list-group-item-action" to="/details/ABW">
            <img src="https://flagpedia.net/data/flags/icon/72x54/aw.png">
            <p>Aruba</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/AFG">
            <img src="https://flagpedia.net/data/flags/icon/72x54/af.png">
            <p>Afghanistan</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/AGO">
            <img src="https://flagpedia.net/data/flags/icon/72x54/ao.png">
            <p>Angola</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/AIA">
            <img src="https://flagpedia.net/data/flags/icon/72x54/ai.png">
            <p>Anguilla</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/ALA">
            <img src="https://flagpedia.net/data/flags/icon/72x54/ax.png">
            <p>Åland Islands</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/ALB">
            <img src="https://flagpedia.net/data/flags/icon/72x54/al.png">
            <p>Albania</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/AND">
            <img src="https://flagpedia.net/data/flags/icon/72x54/ad.png">
            <p>Andorra</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/ARE">
            <img src="https://flagpedia.net/data/flags/icon/72x54/ae.png">
            <p>United Arab Emirates</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/ARG">
            <img src="https://flagpedia.net/data/flags/icon/72x54/ar.png">
            <p>Argentina</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/ARM">
            <img src="https://flagpedia.net/data/flags/icon/72x54/am.png">
            <p>Armenia</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/ASM">
            <img src="https://flagpedia.net/data/flags/icon/72x54/as.png">
            <p>American Samoa</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/ATA">
            <img src="https://flagpedia.net/data/flags/icon/72x54/aq.png">
            <p>Antarctica</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/FLK">
            <img src="https://flagpedia.net/data/flags/icon/72x54/fk.png">
            <p>Falkland Islands</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action active" to="/details/FRA">
            <img src="https://flagpedia.net/data/flags/icon/72x54/fr.png">
            <p>France</p>
          </router-link>
          <router-link class="list-group-item list-group-item-action" to="/details/ZWE">
            <img src="https://flagpedia.net/data/flags/icon/72x54/zw.png">
            <p>Zimbabwe</p>
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CountriesListComponent',
};
</script>
