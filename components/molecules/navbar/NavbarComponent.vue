<template>
  <b-navbar
    :class="$style.navbar"
    class="bg-white"
    toggleable="md"
    fixed="top"
    type="light"
    variant="primary"
  >
    <b-navbar-brand v-b-toggle.sidebar-1 :class="$style.sidebarToggle" href="#"
      >[M]</b-navbar-brand
    >

    <!-- side nav on sm and md -->
    <b-sidebar id="sidebar-1" shadow>
      <side-nav-component></side-nav-component>
    </b-sidebar>
    <!-- end of side nav -->
    <b-nav-text class="h4 mb-0">{{ route }}</b-nav-text>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto bg-white">
        <b-nav-form>
          <b-form-input
            size="sm"
            class="mr-sm-2"
            placeholder="Search"
          ></b-form-input>
          <b-button size="sm" class="btn btn-primary my-2 my-sm-0" type="submit"
            > + New home</b-button
          >
        </b-nav-form>

        <b-nav-item-dropdown right>
          <!-- Using 'button-content' slot -->
          <template #button-content>
            <b-avatar size="md" src="" />
          </template>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue'
import SideNavComponent from '../sidenav/SideNavComponent.vue'
// '../../../assets'

export default defineComponent({
  name: 'NavbarComponent',
  components: { SideNavComponent },
  setup() {
    const sideNavToggle = ref<boolean>(false)

    return {
      sideNavToggle,
    }
  },
  computed: {
    route() {
      return this.$route.name === 'index' && 'Home'
    },
  },
  methods: {
    showToggleBtn(val: boolean) {
      if (val) {
        this.sideNavToggle = val
      }
    },
  },
})
</script>
<style module scoped>
@value breakpoints: '../../../assets/css/main.css';
@value md, lg from breakpoints;
.navbar {
  height: 70px;
  border-bottom: 0.02rem solid var(--grey);
}
.sidebarToggle {
  display: block;
}

b-sidebar {
  width: 30px !important;
}

@media (min-width: lg) {
  .sidebarToggle {
    display: none;
  }
}
</style>
