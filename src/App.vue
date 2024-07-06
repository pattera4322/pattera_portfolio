<script setup>
import { ref } from "vue";
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";

const showHeader = ref(true);
const toggleHeader = () => {
  showHeader.value = !showHeader.value;
};
</script>

<template>
    <header v-show="showHeader">
      <img
        alt="Cat logo"
        class="logo"
        src="@/assets/cat.gif"
        width="155"
        height="155"
      />

      <div class="wrapper">
        <HelloWorld msg="Hi!" />

        <nav>
          <RouterLink to="/">Home</RouterLink>
          <RouterLink to="/about">About</RouterLink>
          <RouterLink to="/portfolio">Portfolio</RouterLink>
          <RouterLink to="/contact">Contact</RouterLink>
        </nav>
      </div>
    </header>

    <!-- <div class="hideButton">
    <button @click="toggleHeader">{{ showHeader ? "Hide" : "Show" }}</button>
  </div> -->

    <main>
      <RouterView />
    </main>
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  padding-bottom: 15px;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

button {
  border-style: solid;
  border-width: 1px;
}

.hideButton {
  text-align: center;
  transition: color 3s;
}
.hideButton :hover {
  text-align: center;
  color: rgb(26, 227, 167);
  font-size: large;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    align-items: center; 
    justify-content: stretch;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
  .hideButton {
    writing-mode: vertical-lr;
  }

}
</style>
