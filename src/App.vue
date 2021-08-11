<template>
  <div id="app">
    <ProductOverview />
  </div>
</template>

<script>
import ProductOverview from "./components/ProductOverview.vue";

export default {
  name: "App",
  components: { ProductOverview },
};
</script>

<style>
#app {
  @apply antialiased flex flex-col items-center mt-4;
}
</style>
