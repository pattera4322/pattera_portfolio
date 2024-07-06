<script setup></script>

<template>
  <div>
    <h2>Capstone project</h2>
    <p>Project Name: SMART STOCK</p>
    <br>
    <div class="video-container">
      <iframe
        width="560"
        height="315"
        src="https://www.youtube.com/embed/3_86KGH8dko?si=8Q8hI7dikVMVcm1d"
        title="YouTube video player"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
        referrerpolicy="strict-origin-when-cross-origin"
        allowfullscreen
      ></iframe>
    </div>
  </div>
</template>

<style>
.video-container {
  position: relative;
  width: 100%;
  padding-top: 56.25%;
}

.video-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
@media (min-width: 1024px) {
  iframe {
    /* min-height: 100vh; */
    /* min-width: 30vh; */
    display: flex;
    align-items: center;
  }
}
</style>
