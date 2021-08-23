<template>
  <base-card>
    <base-button @click="setSelectedTab('stored-resources')" 
    :mode="setModeStoredResources"
      >Resources</base-button
    >
    <base-button @click="setSelectedTab('add-resources')"
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
    };
  },
  methods: {
    setSelectedTab(value) {
      this.selectedTab = value;
    },
  },
  computed: {
      setModeStoredResources(){
          return {
              'flat':this.selectedTab === 'stored-resources'  
          }
      },
      setModeAddResources(){
          return {
              'flat': this.selectedTab === 'add-resources'
          }
      }
  }
};
</script>
