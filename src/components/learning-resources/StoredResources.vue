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
// import BaseCard from "../../UI/BaseCard.vue";
import LearningResources from "./LearningResources.vue";
export default {
  components: {
    LearningResources: LearningResources,
  },

  data() {
    return {
      storedResources: [
        {
          id: "official-guide",
          title: "Official Guide",
          description: "The official Vue js Documentation",
          link: "https://vuejs.org",
        },
        {
          id: "google",
          title: "Google",
          description: "Learn How To Search for things",
          link: "https://google.com",
        },
      ],
    };
  },
};
</script>

<style>
ul {
padding: 0;}
</style>
