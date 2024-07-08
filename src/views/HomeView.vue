<script setup></script>

<template>
  <main class="grid-container">
    <img src="@/assets/mint2.png" />
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
main {
  display: flex;
  align-items: center;
  flex-direction: column;
}
img {
  width: 50vw;
  height: 50vw;
  margin-bottom: 20px; 
}
#name {
  color: rgb(222, 76, 76);
  font-weight: bold;
}
.grid-container {
  display: flex;
  flex-direction: column; 
  align-items: center;
}
a:hover {
  padding: 3px 10px;
  text-decoration: underline;
}
a {
  font-weight: 600;
}

@media (min-width: 1024px) {
  main {
    min-height: 100vh;
    align-items: center;
    flex-direction: row; 
    justify-content: center;
    padding: 0;
  }

  img {
    margin-bottom: 0;
    margin-right: 20px; 
    width: 20vw;
    height: 20vw;
  }

  .grid-container {
    flex-direction: row; 
    align-items: center;
  }
}
</style>
