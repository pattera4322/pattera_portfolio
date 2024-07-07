<script setup></script>

<template>
  <main class="grid-container">
    <img src="@/assets/mint2.png" width="300px" height="300px" />
    <p>
      I'm <span id="name">Pattera Jongwatananugul</span>, a recent graduate from
      King Mongkut's University of Technology Thonburi with a background in
      frontend development. I have a keen interest in data analysis, business
      analysis, and UX/UI design roles. I'm passionate about leveraging data to
      drive insights and decisions while creating intuitive and engaging user
      experiences. Explore my
      <router-link to="/portfolio">projects</router-link>,
      <router-link to="/about">skills</router-link>, and
      <router-link to="/about">experiences</router-link> to learn more about my
      journey and how I can contribute to your team.
    </p>
  </main>
</template>

<style scoped>

#name {
  color: rgb(222, 76, 76);
  font-weight: bold;
}
.grid-container {
  display: grid;
  grid-template-columns: auto auto;
  /* background-color: #2196f3; */
  padding: 10px;
}
a:hover {
  /* background-color: rgb(252, 193, 158); */
  padding: 3px 10px;
  text-decoration: underline;
}
a{
  font-weight: 600;
}

@media (min-width: 1024px) {
  main {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
