<script setup>
import ImageSlider from "../ImageSlider.vue";
import profileImage from "@/assets/profile.png";
import findFriend1 from "@/assets/findfriend1.png";
import findFriend2 from "@/assets/findfriend2.png";
import findFriend3 from "@/assets/findfriend3.png";

const images = [findFriend1, profileImage, findFriend2, findFriend3];
</script>

<template>
  <div>
    <h1>UX/UI projects</h1>
    <div>
      <div>
        <h3>Project: Easter Egg Festival</h3>
        <div class="monitor">
          <img src="@/assets/easter.png" alt="Easter Egg Festival Project" />
        </div>
        <a
          href="https://www.figma.com/proto/zWoqivBThp2cEOMQsTe5bO/Untitled?node-id=217-494&t=mlf4CcRKqIKyCheU-1&scaling=min-zoom&content-scaling=fixed&page-id=0%3A1&starting-point-node-id=217%3A494"
          target="_blank"
          class="play"
          ><i class="gg-play-button-o"></i>
          <p>Play Prototype</p></a
        >
        <a
          href="https://www.figma.com/design/zWoqivBThp2cEOMQsTe5bO/Untitled?node-id=0-1&t=jSzPKtDqdOrAEY2n-1"
          target="_blank"
          >Go to see our Design! -></a
        >
      </div>

      <div>
        <h3>Project: Finding Temporary Friend</h3>
        <div class="image-mix">
          <div class="image-slider"></div>
          <ImageSlider :images="images"></ImageSlider>

          <a
            href="https://www.figma.com/proto/mwus5pxiUfW1QBubDCpQvl/%E0%B9%80%E0%B8%9E%E0%B8%B7%E0%B9%88%E0%B8%AD%E0%B8%99%E0%B8%8A%E0%B8%B1%E0%B9%88%E0%B8%A7%E0%B8%84%E0%B8%A3%E0%B8%B2%E0%B8%A7?node-id=13-8&t=bv7jl79FwF3IOPFY-0&scaling=scale-down&content-scaling=fixed&page-id=0%3A1"
            target="_blank"
            class="play"
            ><i class="gg-play-button-o"></i>
            <p>Play Prototype</p></a
          >
        </div>
        <a
          href="https://www.figma.com/design/mwus5pxiUfW1QBubDCpQvl/%E0%B9%80%E0%B8%9E%E0%B8%B7%E0%B9%88%E0%B8%AD%E0%B8%99%E0%B8%8A%E0%B8%B1%E0%B9%88%E0%B8%A7%E0%B8%84%E0%B8%A3%E0%B8%B2%E0%B8%A7?node-id=0-1&t=FOwieKCkj5NNTrL8-1"
          target="_blank"
          >Go to see our Design! -></a
        >
      </div>
    </div>
  </div>
</template>

<style scoped>
.monitor {
  height: 56.25vh;
  width: 100%;
  overflow: auto;
}

.monitor img {
  width: 100%;
  height: auto;
}

h3 {
  font-size: 1.3rem;
  font-weight: 500;
  margin: 1.7rem 0rem;
  color: var(--color-heading);
}

h2 {
  font-size: 1.4rem;
  font-weight: 600;
  color: var(--color-heading);
}
.play {
  display: flex;
  align-content: center;
  justify-content: center;
  gap: 8px;
  color: var(--color-text);
  padding: 8px;
}

a:hover {
  border-radius: 2px;
}

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
.image-slider {
  width: 35%;
}
.image-mix {
  display: flex;
  justify-content: center;
  align-content: center;
  align-items: center;
  flex-direction: column;
}
a {
  width: 100%;
}
</style>
