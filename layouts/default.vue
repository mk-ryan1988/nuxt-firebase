<template>
  <div class="relative">
    <NavBar />

    <main class="pt-16">
      <nuxt />
    </main>
  </div>
</template>

<script lang="ts">
import NavBar from "~/components/Navigation/NavBar.vue";

export default {
  components: {
    NavBar
  }
}
</script>

<style>

</style>
