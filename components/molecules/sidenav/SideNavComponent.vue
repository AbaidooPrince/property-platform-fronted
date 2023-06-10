<template>
  <b-navbar :class="$style.navbar" class="bg-white" toggleable type="light">
    <b-navbar-brand href="#"><icon-grid></icon-grid></b-navbar-brand>



  </b-navbar>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
import IconGrid from '~/icons/IconGrid.vue'

export default defineComponent({
  name: 'SideNavComponent',
  components: { IconGrid },
  setup() {
    const routes = ['/dashboard', '/properties', '/agents', 'reports', '/settings', '/user']
    return {
      routes
    }
  },
})
</script>
<style module scoped>
.navbar {
  /* display: ; */
  border-right: 0.02rem solid var(--grey);
}

.nav-link {
  padding: 0 !important;
}
.navbarIcon{
  list-style: none;
}
</style>
