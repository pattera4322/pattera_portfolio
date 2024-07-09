<script setup></script>

<template>
  <main>
    <div>
      <img src="@/assets/email.png" alt="email" /><a
        href="mailto:pattera.jw@hotmail.com?subject=Hello%20Pattera&body=Dear%20Pattera%20Jongwatananugul,"
        >pattera.jw@hotmail.com</a
      >
    </div>

    <div>
      <img src="@/assets/call.png" alt="phone" /><a href="tel:0894457114"
        >(+66)89 445 7114</a
      >
    </div>

    <div>
      <img src="@/assets/github.png" alt="github" /><a href="https://github.com/pattera4322">pattera4322</a>
    </div>

    <div>
      <img src="@/assets/linkedin.png" alt="linkedIn" /><a
        href="https://www.linkedin.com/in/pattera4322/"
        >My LinkedIn</a
      >
    </div>
  </main>
</template>

<style scoped>
main {
  display: flex;
  align-items: center;
  flex-direction: column;
gap: 15px;
}
main > div{
  display: flex;
  width: 50vw;
  align-items: center;
  gap: 15px;
}
div > img{
  width: 10vw;
  height: 10vw;
  background: var(--color-background-img);
  padding: 2px;
  border-radius: 80px;
}
a{
  transition: 0.5s;
  color: var(--color-text);
  font-weight: 600;
  font-size: medium;
}
a:hover{
  font-size: larger;
  padding: 0px 10px;
}
@media (min-width: 1024px) {
  main {
    min-height: 100vh;
    flex-direction: row;
    justify-content: space-between;
    padding: 0%;
  }
  main > div {
    display: flex;
    /* align-content: center; */
    justify-content: center;
    flex-direction: column;
    width: 25vw;
  }
  img{
    width: 3vw;
    height: 3vw;
  }
  a{
    
  }
}
</style>
