<script setup>
import { ref } from "vue";
import HelloWorld from "./components/HelloWorld.vue";

const showHeader = ref(true);
const toggleHeader = () => {
  showHeader.value = !showHeader.value;
};
</script>

<template>
  <div :class="{ open: showHeader, container: true }">
    <header :class="{ open: showHeader }">
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

    <button :class="{ open: showHeader }" @click="toggleHeader">
      {{ showHeader ? "Hide" : "Show" }}
    </button>

    <main :class="{ shift: showHeader }">
      <RouterView />
    </main>
  </div>
</template>

<style scoped>
header {
  width: 100%;
  height: 0;
  position: fixed;
  z-index: 1;
  top: 0;
  left: 0;
  background-color: #bafbe9;
  overflow-y: hidden;
  transition: height 0.5s, width 0.5s;
  /* padding-top: 60px; */
  display: flex;
  flex-direction: row;
  align-items: center;
}

header.open {
  height: 35vh; /* Use vh units to set height relative to viewport */
}

header .logo {
  display: block;
  margin: 0 auto 2rem;
}

header .wrapper {
  width: 100%;
  text-align: center;
}

header nav {
  width: 100%;
  font-size: 17px;
  margin-top: 1rem;
  display: inline-block;
}

header nav a {
  display: inline-block;
  padding: 8px 15px;
  text-decoration: none;
  color: #818181;
  transition: color 0.3s;
}

header nav a.router-link-exact-active {
  color: var(--color-text);
  background-color: hsla(160, 100%, 37%, 0.2);
  border-radius: 40px;
}

header nav a:hover {
  color: #f1f1f1;
}

button {
  position: fixed;
  top: 0;
  right: 0;
  z-index: 2;
  padding: 5px 28px;
  border-radius: 0px 0px 8px 8px;
  border-color: white;
  transition: 0.5s;
}

button.open {
    top:35vh;
    margin: auto;
    right: 0;
  
  }

button:hover {
  background-color: hsla(160, 100%, 37%, 0.2);
  border-color:  hsla(160, 100%, 37%, 0.2);
}

main {
  top: 0;
  transition: margin-top 0.5s, margin-left 0.5s;
}

main.shift {
  margin-top: 35vh;
  padding-right: 0px;
}

/* Styles for larger screens */
@media (min-width: 1024px) {
  header {
    width: 0;
    height: 100%;
    top: 0;
    left: 0;
    padding-top: 60px;
    overflow-x: hidden;
    overflow-y: auto;
    transition: width 0.5s;
    flex-direction: row;
  }

  header.open {
    width: 40vw; /* Use vw units to set width relative to viewport */
    height: 100%;
    padding: 0px 20px;
  }

  header .logo {
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

  button.open {
    writing-mode: vertical-lr;
    margin: auto;
    right: auto;
    left: 40vw;
    top:0;
  }

  button {
    writing-mode: vertical-lr;
    right: auto;
    margin: auto;
    left: 0;
    transition: 0.5s;
    padding: 28px 5px;
    border-radius: 0px 8px 8px 0px;
    top:0;
  }

  main {
    transition: margin-left 0.5s, width 0.5s;
    width: 100%;
  }

  main.shift {
    margin-top: 0px;
    margin-left: 40vw;
    width: 50%;
    /* padding-right:100px; */
  }
}
</style>
