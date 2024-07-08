<script setup>
import SlotItem from "../SlotItem.vue";
</script>

<template>
  <main>
    <h1>Capstone Project</h1>
    <br />
    <h2>Project: SMART STOCK</h2>
    <br />
    <div class="container-main">
      <div class="main video-container">
        <iframe
          src="https://www.youtube.com/embed/3_86KGH8dko?si=8Q8hI7dikVMVcm1d"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
          referrerpolicy="strict-origin-when-cross-origin"
          allowfullscreen
        ></iframe>
      </div>

      <div class="detail">
        In today's volatile business environment, effective sales and stock
        management are crucial for maintaining customer satisfaction and
        long-term profitability. Our project focuses on analyzing and
        forecasting sales and stock to optimize warehouse management, preventing
        excess or shortage of products. By employing statistical models to
        predict sales trends and stock levels, we enhance resource management
        and reduce business expenses. This helps in strategic product ordering
        and future marketing planning.
      </div>
    </div>
    <h3>Core Features</h3>
    <div class="container-features">
      <SlotItem :showIcon="false">
        <template #image
          ><img src="@/assets/dashboard.png" alt="dashboard icon"
        /></template>

        <template #heading>Data to Dashboard</template>

        <p>
          Express a prediction of sales trends and the quantity of sole
          products. Furthermore, the dashboard displays the necessary analytical
          data for future stock planning.
        </p>
      </SlotItem>

      <SlotItem :showIcon="false">
        <template #image
          ><img src="@/assets/predictive.png" alt="predictive icon"
        /></template>

        <template #heading>Predictive Data</template>

        <p>
          To display the forecasting data to help decision-making for product
          procurement and compare sales trends and the quantity of products in
          the future.
        </p>
      </SlotItem>

      <SlotItem :showIcon="false">
        <template #image
          ><img src="@/assets/newspaper.png" alt="newspaper icon"
        /></template>

        <template #heading>Economy news</template>

        <p>
          Presentation of economic news associated with the product via a
          dashboard page.
        </p>
      </SlotItem>
    </div>

    <h3>Tools & Technology</h3>
    <div class="image-container">
      <img src="@/assets/techStacks.jpg" alt="tech-stack" />
    </div>
  </main>
</template>

<style scoped>
.container-features img {
  width: 40px;
  height: 40px;
}

.video-container {
  position: relative;
  width: 100%;
  padding-top: 56.25%;
}

.video-container iframe{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

.image-container {
  position: relative;
  width: 100%;
  padding-top: 56.25%;
}

.image-container img{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}

h3 {
  font-size: 1.3rem;
  font-weight: 500;
  margin-top: 1.7rem;
  color: var(--color-heading);
}

h2 {
  font-size: 1.4rem;
  font-weight: 600;
  color: var(--color-heading);
}

@media (min-width: 1024px) {
  /* main{
    padding: 0rem 5rem;
  } */

  .video-container {
    position: relative;
    width: 50%;
    padding-top: 27.25%;
  }

  .container-main {
    display: flex;
    flex-wrap: nowrap;
    align-items: stretch;
    justify-content: space-between;
    gap: 0px 20px;
  }

  .detail {
    width: 50%;
  }

  .container-features {
    display: flex;
    flex-wrap: nowrap;
    justify-content: space-around;
  }

  .item {
    margin-top: 2rem;
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
