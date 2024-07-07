<template>
  <main class="grid-container">
    <!-- <h1>This is an about page</h1> -->
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
      >. My coursework and projects have given me a strong understanding of how
      to build and maintain functional and aesthetically pleasing web
      applications.
    </p>
  </main>
</template>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: auto auto;
  /* background-color: #2196f3; */
  padding: 10px;
  align-items: center;
}
.logo {
  width: 12vw;
  height: 15vw;
}
.icon {
  color: rgb(39, 177, 161);
  display: inline-flex;
  align-items: center;
  font-weight:500;
  transition: 0.5s;
}
.icon:hover{
  /* cursor: pointer; */
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
@media (min-width: 1024px) {
  main {
    min-height: 100vh;
    display: flex;
    align-items: center;
    /* flex-direction: column; */
  }
}
</style>
