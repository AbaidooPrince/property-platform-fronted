<template>
  <div :class="$style.mainWrapper">
    <div :class="$style.filterColumn">
    <filter-view></filter-view>
  </div>
    <b-row cols="12" :class="$style.propertiesWrapper">
      <b-col v-for="(property, p) in properties" :key="p" sm="12" md="6" lg="4" xl="4" class="pb-4">
          <property-card :agent="property.agent" :image="property.image"></property-card>
      </b-col>
    </b-row>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import mockData from '../store/mock'
import FilterView from '~/components/organisms/filter/FilterView.vue';
import PropertyCard from '~/components/molecules/property/PropertyCard.vue';

export default defineComponent({
  name: 'IndexPage',
  components: { FilterView, PropertyCard },
  layout: 'dashboard',
  setup() {
    const properties = mockData

    return {
      properties
    }
  },
  // async asyncData({ $axios}) {
  //   let { data } = await $axios.get('/properties')
  // }
})
</script>
<style module scoped>

@value breakpoints: '../assets/css/main.css';
@value md, lg from breakpoints;
.filterColumn {
  width: 0;
  padding: 1rem;
}

@media (min-width: lg) {
  .filterColumn {
    width: 250px;
    height: 100vh;
    /* padding: 2rem; */
    border-right: 0.02rem solid var(--grey);
  }
  .mainWrapper {
  padding: 0 2rem;
  display: grid;
  grid-template-columns: auto 1fr;
}

.propertiesWrapper {
  padding: 2rem;
}
}
</style>
