<template>
  <ul>
    <base-card>
      <learning-resources
        v-for="res in storedResources"
        :res="res"
        :key="res.id"
      ></learning-resources>
    </base-card>
  </ul>
</template>

<script>

import LearningResources from "./LearningResources.vue";
export default {
  components: {
    LearningResources: LearningResources,
  },
inject: ["storedResources"],

};
</script>

<style>
ul {
padding: 0;}
</style>
