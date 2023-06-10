<template>
  <div :class="$style.filterWrapper">
    <div>
      <div
        v-b-toggle.country-collapse
        aria-expanded="true"
        :class="$style.filterHeader"
      >
        <label :class="$style.filterHeaderTitle">{{ country.title }}</label>
        <icon-chevron direction="down"></icon-chevron>
      </div>
      <b-collapse v-show="true" id="country-collapse">
        <b-form-checkbox-group
          v-model="selectedCountries"
          :options="country.data"
          class="mb-3"
          value-field="value"
          text-field="name"
          disabled-field="notEnabled"
          stacked
        ></b-form-checkbox-group>
      </b-collapse>
    </div>
    <div>
      <div
        v-b-toggle.type-collapse
        aria-expanded="true"
        :class="$style.filterHeader"
      >
        <label :class="$style.filterHeaderTitle">{{ estateType.title }}</label>
        <icon-chevron direction="down"></icon-chevron>
      </div>
      <b-collapse v-show="true" id="type-collapse">
        <b-form-checkbox-group
          v-model="selectedEstateType"
          :options="estateType.data"
          class="mb-3"
          value-field="value"
          text-field="name"
          disabled-field="notEnabled"
          stacked
        ></b-form-checkbox-group>
      </b-collapse>
    </div>
  </div>
</template>
<script lang="ts">
import { ref } from 'vue'
import IconChevron from '../../../icons/IconChevron.vue'
export default {
  components: { IconChevron },
}
</script>
<script lang="ts" setup>
const selectedCountries = ref([{ name: 'Australia', value: 1 }])
const selectedEstateType = ref([{ name: 'Apartment', value: 1 }])
const country = {
  title: 'Country',
  data: [
    { name: 'Australia', value: 1 },
    { name: 'Algeria', value: 2 },
    { name: 'Belgium', value: 3 },
    { name: 'Bulgaria', value: 4 },
    { name: 'China', value: 5 },
    { name: 'Estonia', value: 6 },
  ],
}
const estateType = {
  title: 'Estate Type',
  data: [
    { name: 'Apartment', value: 1 },
    { name: 'Mansion', value: 2 },
    { name: 'Summerhouse', value: 3 },
    { name: 'Plaza', value: 4 },
  ],
}
</script>

<style module scoped>
@value breakpoints: '../../../assets/css/main.css';
@value md, lg from breakpoints;
.filterWrapper {
  display: flex;
  /* justify-content: space-between; */
}
.filterHeader {
  display: flex;
  justify-content: space-between;
  width: 5rem;
}
.filterHeaderTitle {
  font-weight: bold;
  font-size: medium;
}

@media (min-width: lg) {
  .filterHeader {
    width: auto;
  }
  .filterWrapper {
    display: inline;
  }
}
</style>
