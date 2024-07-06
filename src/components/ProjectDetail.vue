<script setup>
import SlotItem from "./SlotItem.vue";
import DocumentationIcon from "./icons/IconDocumentation.vue";
import ToolingIcon from "./icons/IconTooling.vue";
import EcosystemIcon from "./icons/IconEcosystem.vue";
import CommunityIcon from "./icons/IconCommunity.vue";
import SupportIcon from "./icons/IconSupport.vue";
import { RouterLink, RouterView } from "vue-router";

</script>

<template>
  <!-- <h1>My Project</h1> -->

  <SlotItem>
    <template #icon>
      <DocumentationIcon />
    </template>
    <template #heading>Capstone Project</template>

    <p>
      This project involves analyzing sales and inventory data to predict future
      trends using machine learning techniques in a web application.
    </p>
    <RouterLink to="/portfolio/project/1">See more -></RouterLink>
  </SlotItem>

  <SlotItem>
    <template #icon>
      <ToolingIcon />
    </template>
    <template #heading>Integrated Project</template>

    <p>This project is about a meeting reservation web application.</p>
  
    <RouterLink to="/portfolio/project/2">See more -></RouterLink>
  </SlotItem>

  <SlotItem>
    <template #icon>
      <EcosystemIcon />
    </template>
    <template #heading>UX/UI Projects</template>
    <p>These projects are all about design web application and mobile application interface.</p>
    <RouterLink to="/portfolio/project/3">See more -></RouterLink>
  </SlotItem>

  <SlotItem>
    <template #icon>
      <CommunityIcon />
    </template>
    <template #heading>Data Projects</template>
    <p>
      These projects are all about data analysis and machine learning.
    </p>
    <RouterLink to="/portfolio/project/4">See more -></RouterLink>

  </SlotItem>
</template>
