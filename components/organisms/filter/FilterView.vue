<template>
  <div>
    <div v-b-toggle.my-collapse aria-expanded="true" :class="$style.filterHeader">
    <label variant="transparent"
      >{{ data.title }}</label
    >
    <icon-chevron direction="down"></icon-chevron>
    </div>
    <b-collapse v-show="true" id="my-collapse"> 
        <b-form-checkbox-group
      v-model="selectedCountries"
      :options="data.data"
      class="mb-3"
      value-field="value"
      text-field="name"
      disabled-field="notEnabled"
      stacked
    ></b-form-checkbox-group>
    </b-collapse>
  </div>
</template>
<script lang="ts" setup>

import { reactive } from 'vue'
const selectedCountries = reactive([{name: 'Australia', value: 1}])
const data = 
      {
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

</script>
<script lang="ts">
import IconChevron from '../../../icons/IconChevron.vue'
export default {
  components: { IconChevron }
}
</script>

<style module scoped>
.filterHeader {
  display: flex;
  justify-content: space-between;
}
</style>
