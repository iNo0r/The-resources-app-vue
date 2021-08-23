<template>
  <div>
    <TheHeader />
    <the-resources></the-resources>
  </div>
</template>

<script>
import TheHeader from "./layouts/TheHeader.vue"; 
import TheResources from "./components/learning-resources/TheResources.vue";

export default {
  components: {
    TheHeader: TheHeader,
    TheResources: TheResources,
  },
};
</script>

<style>
body,html {
  margin: 0%;
}
</style>
