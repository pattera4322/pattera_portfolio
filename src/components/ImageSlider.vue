  
  <script setup>
  import { ref } from 'vue';
  
  const props = defineProps({
    images: {
      type: Array,
      required: true
    }
  });
  
  const currentIndex = ref(0);
  
  function nextSlide() {
    if (currentIndex.value < props.images.length - 1) {
      currentIndex.value++;
    } else {
      currentIndex.value = 0;
    }
  }
  
  function prevSlide() {
    if (currentIndex.value > 0) {
      currentIndex.value--;
    } else {
      currentIndex.value = props.images.length - 1;
    }
  }
  
  function goToSlide(index) {
    currentIndex.value = index;
  }
  </script>

<template>
    <div class="image-slider">
      <div class="slider-window">
        <div class="slider-content" :style="{ transform: `translateX(-${currentIndex * 100}%)` }">
          <div class="slide" v-for="(image, index) in images" :key="index">
            <img :src=image alt="">
          </div>
        </div>
      </div>
      <button class="prev-button" @click="prevSlide"><i class="gg-chevron-left"></i></button>
      <button class="next-button" @click="nextSlide"><i class="gg-chevron-right"></i></button>
      <div class="dots">
        <span v-for="(image, index) in images" :key="index" :class="{ active: currentIndex === index }" @click="goToSlide(index)"></span>
      </div>
    </div>
  </template>

  
  <style scoped>
  .image-slider {
    position: relative;
    width: 100%;
    overflow: hidden;
    border-radius: 15px;
  }
  
  .slider-window {
    width: 100%;
    overflow: hidden;
  }
  
  .slider-content {
    display: flex;
    transition: transform 0.5s ease-in-out;
  }
  
  .slide {
    min-width: 100%;
    transition: opacity 1s;
  }
  
  .slide img {
    width: 100%;
    display: block;
    border-radius: 15px;
  }
  
  .prev-button,
  .next-button {
    position: absolute;
    top: 50%;
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    padding: 15px 2px;
    cursor: pointer;
    border-radius: 10px;
    transition: 0.3s;
  }
  
  .prev-button {
    left: 10px;
  }
  
  .next-button {
    right: 10px;
  }

  .prev-button:hover,
  .next-button:hover {

    background-color: rgb(102, 255, 181);

  }
  
  .dots {
    position: absolute;
    bottom: 10px;
    left: 50%;
    transform: translateX(-50%);
    display: flex;
    gap: 5px;
  }
  
  .dots span {
    display: inline-block;
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background-color: rgba(255, 255, 255, 0.5);
    cursor: pointer;
    transition: background-color 0.3s;
  }
  
  .dots span.active {
    background-color: rgba(255, 255, 255, 1);
  }
  </style>
  