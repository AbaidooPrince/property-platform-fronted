<template>
  <b-navbar :class="$style.navbar" class="bg-white" toggleable type="light">
    <b-navbar-brand href="#">[M]</b-navbar-brand>

  </b-navbar>
</template>
<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'SideNavComponent',
  setup() {},
})
</script>
<style module scoped>
.navbar {
  display: list-item;
  border-right: 0.02rem solid var(--grey);
}
</style>
