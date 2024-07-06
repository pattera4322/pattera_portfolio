<script>
import CapstoneProject from "../components/ProjectComponents/CapstoneProject.vue";
import IntegratedProject from "../components/ProjectComponents/IntegratedProject.vue";
import DesignProject from "../components/ProjectComponents/DesignProject.vue";
import DataProject from "../components/ProjectComponents/DataProject.vue";

export default {
  components: {
    CapstoneProject,
    IntegratedProject,
    DesignProject,
    DataProject,
  },
  computed: {
    currentComponent() {
      const id = this.$route.params.id;
      if (id === "1") {
        return "CapstoneProject";
      } else if (id === "2") {
        return "IntegratedProject";
      } else if (id === "3") {
        return "DesignProject";
      } else if (id === "4") {
        return "DataProject";
      }
      return null; // or a default component
    },
  },
};
</script>

<template>
  <div>
    <router-link to="/portfolio"><- Go Back</router-link>
    <component :is="currentComponent" />
  </div>
</template>
