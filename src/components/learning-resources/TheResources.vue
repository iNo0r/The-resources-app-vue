<template>
  <base-card>
    <base-button
      @click="setSelectedTab('stored-resources')"
      :mode="setModeStoredResources"
      >Resources</base-button
    >
    <base-button
      @click="setSelectedTab('add-resources')"
      :mode="setModeAddResources"
      >Add Resources</base-button
    >
  </base-card>
  <component :is="selectedTab"></component>
</template>

<script>
import StoredResources from "./StoredResources.vue";
import AddResources from "./AddResources.vue";

export default {
  components: {
    StoredResources: StoredResources,
    AddResources: AddResources,
  },
  data() {
    return {
      selectedTab: "stored-resources",
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
  provide() {
    return {
      // this data is used in StoredResources.vue
      storedResources: this.storedResources,
      // this method is used in AddResources.vue
      funAddNewResource: this.funAddNewResource,
    };
  },

  methods: {
    setSelectedTab(value) {
      this.selectedTab = value;
    },
    funAddNewResource(title,description,link) {
      const newResource = {
        id: new Date().toISOString(),
        title : title,
        description:description,
        link:link,
      }
      this.storedResources.push(newResource);
    },
  },
  computed: {
    setModeStoredResources() {
      return {
        flat: this.selectedTab === "stored-resources",
      };
    },
    setModeAddResources() {
      return {
        flat: this.selectedTab === "add-resources",
      };
    },
  },
};
</script>
