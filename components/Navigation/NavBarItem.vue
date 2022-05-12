<template>
    <NuxtLink
      v-if="item"
      :to="item.to"
      aria-current="page"
      class="block px-3 py-2 rounded-md text-base font-medium hover:bg-black hover:text-white"
    >
      {{ item.name }}
    </NuxtLink>
</template>

<script>
export default {
  name: 'NavBarItem',
  props: {
    item: {
      type: Object,
      default: undefined
    },
  },
}
</script>

<style>
 .nuxt-link-active {
   @apply bg-black text-white;
 }
</style>
