<template>
  <div>
    <side-nav-component :class="$style.sidenav"></side-nav-component>
    <navbar-component :class="$style.navbar"></navbar-component>

    <main :class="$style.main">
      <Nuxt />
    </main>
  </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
import NavbarComponent from '~/components/molecules/navbar/NavbarComponent.vue'
import SideNavComponent from '~/components/molecules/sidenav/SideNavComponent.vue'

export default defineComponent({
  components: { NavbarComponent, SideNavComponent },
  setup() {},
})
</script>
<style scoped module>
@value breakpoints: '../assets/css/main.css';
@value sm, md, lg from breakpoints;
.sidenav {
  display: none;
  position: fixed;
  width: 5%;
  height: 100vh;
}

.navbar {
  /* position: sticky; */
}

.main {
  position: absolute;
  height: 100vh;
  width: 100%;
}

@media (min-width: md) {
  .main {
    position: relative;
  }
}

@media (min-width: lg) {
  .sidenav {
    display: block;
  }

  .navbar {
    width: 95%;
    left: 5%;
  }
  .main {
    position: absolute;
    left: 5%;
    top: 10%;
    width: 95%;
    margin: 0;
  }
}
</style>
