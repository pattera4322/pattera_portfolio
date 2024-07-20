<script setup>
import SlotItem from "../SlotItem.vue";
</script>

<template>
  <main>
    <h1>Integrated Project</h1>
    <br />
    <h2>Project: Online Reservation System for Advisor Meetings</h2>
    <br />
    <p>
      Developed a comprehensive online system for managing advisor meetings,
      enabling users to create, reserve, and cancel appointments with advisors
      efficiently.
    </p>
    <h3>Core Features</h3>
    <div class="container-features">
      <SlotItem :showIcon="false">
        <template #image
          ><img src="@/assets/create.png" alt="create icon"
        /></template>

        <template #heading>Meeting Creation</template>

        <p>
          Advisors can set up available meeting slots, specifying dates, times,
          and other relevant details.
        </p>
      </SlotItem>

      <SlotItem :showIcon="false">
        <template #image
          ><img src="@/assets/cancel.png" alt="cancel icon"
        /></template>

        <template #heading>Reservation System</template>

        <p>
          Users can easily browse available slots and reserve meetings with
          their chosen advisor.
        </p>
      </SlotItem>

      <SlotItem :showIcon="false">
        <template #image
          ><img src="@/assets/reserve.png" alt="reserve icon"
        /></template>

        <template #heading>Cancellation Feature</template>

        <p>
          Users have the flexibility to cancel or reschedule their appointments
          as needed, ensuring maximum convenience and efficient time management.
        </p>
      </SlotItem>
    </div>

    <h3>Tools & Technology</h3>
    <div class="image-container">
      <img src="@/assets/toolProj2.png" alt="tech-stack" />
    </div>
  </main>
</template>

<style scoped>
.item img {
  background: var(--color-background-img);
  border-radius: 5px;
  padding: 2px;
  width: 40px;
  height: 40px;
}
h2 {
  font-size: 1.4rem;
  font-weight: 600;
  color: var(--color-heading);
  border-bottom: 4px solid rgb(56, 226, 169);
}

h3 {
  font-size: 1.3rem;
  font-weight: 500;
  margin: 1.7rem 0rem 1.3rem 0rem;
  color: var(--color-heading);
}

.image-container {
  position: relative;
  width: 100%;
  padding-top: 56.25%;
  border-radius: 20px;
}

.image-container img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
@media (min-width: 1024px) {
  .container-features {
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-around;
  }
  .item {
    /* margin-top: 2rem; */
    display: flex;
    align-content: center;
    padding: 0px;
    width: 33%;
  }
  .item:before,
  .item:after {
    border: none;
  }
}
</style>
