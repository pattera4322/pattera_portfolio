<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import ImageSlider from "../components/ImageSlider.vue";
import accentureImage from '@/assets/accenture.jpg';
import teamImage from '@/assets/team.jpg';

const images = [accentureImage, teamImage];

const sections = ref(["section-one", "section-two", "section-three"]);
const activeSectionIndex = ref(0);
const windowWidth = ref(window.innerWidth);

const updateWindowWidth = () => {
  windowWidth.value = window.innerWidth;
};

let observer;

onMounted(() => {
  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          const sectionId = entry.target.id;
          setActiveSection(sectionId);
        }
      });
    },
    { threshold: 0.5 }
  );

  sections.value.forEach((sectionId) => {
    const target = document.getElementById(sectionId);
    if (target) {
      observer.observe(target);
    }
  });

  window.addEventListener("resize", updateWindowWidth);
});

onUnmounted(() => {
  window.removeEventListener("resize", updateWindowWidth);
});

function setActiveSection(sectionId) {
  const sectionIndex = sections.value.indexOf(sectionId);
  if (sectionIndex !== -1) {
    activeSectionIndex.value = sectionIndex;
  }
}

function scrollToSection(sectionId) {
  const sectionIndex = sections.value.indexOf(sectionId);
  if (sectionIndex !== -1) {
    const section = document.getElementById(sectionId);
    if (section) {
      section.scrollIntoView({ behavior: "smooth" });
      setActiveSection(sectionId);
    }
  }
}

function scrollDown() {
  if (activeSectionIndex.value < sections.value.length - 1) {
    activeSectionIndex.value++;
    scrollToSection(sections.value[activeSectionIndex.value]);
  }
}

function scrollUp() {
  if (activeSectionIndex.value > 0) {
    activeSectionIndex.value--;
    scrollToSection(sections.value[activeSectionIndex.value]);
  }
}
</script>

<template>
  <main>
    <div
      id="section-one"
      class="section grid-container"
      :class="{ active: activeSectionIndex === 0 }"
    >
      <img src="@/assets/kmutt.png" alt="kmutt Icon" class="logo" />
      <p>
        During my time at university, I gained knowledge in various programming
        languages and tools, including
        <span class="icon"
          ><img
            src="@/assets/java.png"
            alt="Java Icon"
            class="icon-pic"
          />Java</span
        >,
        <span class="icon"
          ><img
            src="@/assets/js.png"
            alt="js Icon"
            class="icon-pic"
          />JavaScript</span
        >,
        <span class="icon"
          ><img
            src="@/assets/html.png"
            alt="html Icon"
            class="icon-pic"
          />HTML</span
        >,
        <span class="icon"
          ><img
            src="@/assets/css.png"
            alt="css Icon"
            class="icon-pic"
          />CSS</span
        >,
        <span class="icon"
          ><img
            src="@/assets/sql.png"
            alt="sql Icon"
            class="icon-pic"
          />SQL</span
        >, and
        <span class="icon"
          ><img
            src="@/assets/python.png"
            alt="python Icon"
            class="icon-pic"
          />Python</span
        >. My coursework and projects have given me a strong understanding of
        how to build and maintain functional and aesthetically pleasing web
        applications.
      </p>
    </div>

    <div
      id="section-two"
      class="section"
      :class="{ active: activeSectionIndex === 1 }"
    >
      <ImageSlider :images="images"></ImageSlider>
      <p>
        In addition to my academic background, I had the opportunity to intern
        at
        <a
          href="https://www.accenture.com/th-en"
          target="_blank"
          rel="noopener noreferrer"
          >Accenture</a
        >
        as a Frontend Developer. During my internship, I worked on developing a
        mobile banking application using Flutter. This experience allowed me to
        apply my technical skills in a real-world setting, collaborate with a
        professional team, and contribute to a significant project.
      </p>
    </div>

    <div
      id="section-three"
      class="section"
      :class="{ active: activeSectionIndex === 2 }"
    >
      <p>
        Throughout my education and various projects, I've honed essential soft
        skills, including effective communication, teamwork, patience, and
        problem-solving. I believe these skills are crucial for collaborating
        with diverse teams, understanding client needs, and delivering
        successful outcomes.
      </p>
    </div>
    <div v-if="windowWidth > 1024">
      <button class="scroll-button up" @click="scrollUp">
        <i class="gg-chevron-up"></i>
      </button>
      <button class="scroll-button down" @click="scrollDown">
        <i class="gg-chevron-down"></i>
      </button>
    </div>
  </main>
</template>

<style scoped>
html {
  scroll-behavior: smooth;
}

.scroll-button {
  position: fixed;
  bottom: 20px;
  right: 20px;
  background-color: var(--color-background-button);
  border: none;
  border-radius: 50%;
  padding: 10px;
  cursor: pointer;
  transition: background-color 0.3s, transform 0.3s;
  z-index: 1000;
  color: var(--color-text-swip);
}

.scroll-button:hover {
  background-color: rgba(78, 255, 184, 0.8);
  transform: scale(1.1);
  color: azure;
}

.scroll-button i {
  width: 24px;
  height: 24px;
}

.scroll-button.up {
  bottom: 80px;
  right: 20px;
}

.scroll-button.down {
  bottom: 20px;
  right: 20px;
}

.section {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
  transition: opacity 0.5s ease-in-out;
  opacity: 0.4;
}

.section.active {
  opacity: 1;
}

.grid-container {
  display: flex;
  align-items: center;
  flex-direction: column;
  padding: 10px;
}
.logo {
  width: 40vw;
  height: 44vw;
}
.icon {
  color: rgb(39, 177, 161);
  display: inline-flex;
  align-items: center;
  font-weight: 500;
  transition: 0.5s;
}
.icon:hover {
  background-color: rgb(250, 227, 227);
  border-radius: 20px;
  padding: 0px 8px;
}
.icon-pic {
  width: 16px;
  height: 16px;
  margin-right: 4px;
  vertical-align: middle;
}

main {
  position: relative;
}

a {
  font-weight: 600;
  color: rgb(189, 0, 189);
  font-size: large;
}

#section-two {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 20px;
}

@media (min-width: 1024px) {
  main {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    padding: 0;
  }
  .grid-container {
    justify-content: center;
    flex-direction: row;
  }
  .logo {
    width: 12vw;
    height: 15vw;
  }
  .section {
    justify-content: center;
    /* height: calc(100vh - var(--header-height));  */
  }
  #section-two {
    flex-direction: row;
  }
  #section-two p {
    width: 60vw;
  }
}
</style>
