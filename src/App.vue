<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  data() {
    return {
      showHeader: true,
      isBigWindowSize: true,
    };
  },
  components: {
    HelloWorld,
  },
  methods: {
    toggleHeader() {
      this.showHeader = !this.showHeader;
      this.adjustMainMargin();
    },
    adjustMainMargin() {
      if (window.innerWidth < 1024) {
        this.$nextTick(() => {
          const headerHeight = this.$refs.header.offsetHeight;
          this.$refs.main.style.marginTop = this.showHeader
            ? `${headerHeight}px`
            : "0";
          this.$refs.button.style.marginTop = this.showHeader
            ? `${headerHeight}px`
            : "0";
        });
      } else {
        this.$refs.main.style.marginTop = "0";
        this.$refs.button.style.marginTop = "0";
      }
    },
    checkIsBig() {
      if (window.innerWidth < 1024) {
        this.isBigWindowSize = false;
      } else {
        this.isBigWindowSize = true;
      }
    },
  },
  mounted() {
    this.checkIsBig();
    this.adjustMainMargin();
    window.addEventListener("resize", this.adjustMainMargin);
    window.addEventListener("resize", this.checkIsBig);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.adjustMainMargin);
    window.removeEventListener("resize", this.checkIsBig);
  },
};
</script>

<template>
  <div :class="{ open: showHeader, container: true }">
    <header :class="{ open: showHeader }" ref="header">
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

    <button :class="{ open: showHeader }" @click="toggleHeader" ref="button">
      <i
        v-if="showHeader"
        :class="isBigWindowSize ? 'gg-chevron-left' : 'gg-chevron-up'"
      ></i>
      <i
        v-else
        :class="isBigWindowSize ? 'gg-chevron-right' : 'gg-chevron-down'"
      ></i>
    </button>

    <main :class="{ shift: showHeader }" ref="main">
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
  background-color: #c5f1e5;
  overflow-y: hidden;
  transition: 0.5s;
  /* padding-top: 60px; */
  display: flex;
  flex-direction: column;
  align-items: center;
}

header.open {
  height: auto; /* Use vh units to set height relative to viewport */
}

header .logo {
  /* display: block; */
  margin: 0 auto 0rem;
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
  color: #1a7643;
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
  /* top: auto;
    margin: auto; */
  right: 0;
}

button:hover {
  background-color: hsla(0, 0%, 100%, 0.2);
  border-color: hsla(160, 100%, 37%, 0.2);
}

main {
  top: 0;
  padding: 30px 30px;
  transition: margin-top 0.5s, margin-left 0.5s;
}

main.shift {
  margin-top: auto;
}

/* Fade transition styles */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active in <2.1.8 */ {
  opacity: 0;
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
    transition: width 0.8s;
    flex-direction: row;
  }

  header.open {
    width: 40vw; /* Use vw units to set width relative to viewport */
    height: 100%;
    padding: 0px 30px;
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
    margin-top: 0;
    right: auto;
    left: 40vw;
    top: 0;
  }

  button {
    writing-mode: vertical-lr;
    right: auto;
    left: 0;
    transition: 0.8s;
    padding: 28px 5px;
    border-radius: 0px 8px 8px 0px;
    top: 0;
  }

  main {
    transition: margin-left 0.8s, width 0.8s;
    width: 100%;
  }

  main.shift {
    margin-top: 0px;
    margin-left: 40vw;
    width: auto;
  }
}
</style>
