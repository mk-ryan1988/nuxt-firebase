<template>
<nav class="bg-white fixed z-10 w-screen">
  <div class="max-w-7xl mx-auto px-2 sm:px-6 lg:px-8">
    <div class="relative flex items-center justify-between h-16">
      <div class="absolute inset-y-0 left-0 flex items-center sm:hidden">
        <!-- Mobile menu button-->
        <button
          v-if="navItems.length"
          type="button"
          class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-white hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
          aria-controls="mobile-menu"
          aria-expanded="false"
          @click="menuOpen = !menuOpen"
        >
          <span class="sr-only">Open main menu</span>
          <!--
            Icon when menu is closed.
          -->
          <svg v-if="!menuOpen" class="block h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
          <!--
            Icon when menu is open.
          -->
          <svg v-else class="hidden h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
      <div class="flex-1 flex items-center justify-center sm:items-stretch sm:justify-between">
        <div class="flex-shrink-0 flex items-center">
          <Logo />
        </div>
        <div class="hidden sm:block sm:ml-6">
          <div class="flex space-x-4">
            <NavBarItem v-for="item in navItems" :key="`nav-item-${item.key}`" :item="item" />
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- Mobile menu, show/hide based on menu state. -->
  <aside id="mobile-menu" :class="menuOpen ? 'w-screen h-auto' : 'w-0 h-0'" class="absolute left-0 top-16 z-50 shadow-lg rounded-b-sm overflow-x-hidden overflow-y-auto bg-white transform transition-transfom sm:hidden">
    <div class="px-2 pt-2 pb-3 space-y-1">
      <NavBarItem v-for="item in navItems" :key="`nav-item-${item.key}`" :item="item" />
    </div>
  </aside>
</nav>

</template>

<script>
import Logo from "../Logo.vue";
import NavBarItem from "./NavBarItem.vue";

export default {
  name: 'NavBar',
  components: {
    Logo,
    NavBarItem
},
  data() {
    return {
      menuOpen: false,
      navItems: [
        // {
        //   to: '/',
        //   key: 'index',
        //   name: 'Dashboard',
        // },
        // {
        //   to: '/team',
        //   key: 'teamIndex',
        //   name: 'Team',
        // },
        // {
        //   to: '/projects',
        //   key: 'projectsIndex',
        //   name: 'Projects',
        // },
        // {
        //   to: '/calendar',
        //   key: 'calendarIndex',
        //   name: 'Calendar',
        // },
      ]
    }
  },
}
</script>
