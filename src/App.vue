<script setup>
import {ref} from 'vue'

const images = [
  {
    img: 'https://cdn.pixabay.com/photo/2023/06/27/10/51/man-8091933_1280.jpg'
  },
  {
    img: 'https://cdn.pixabay.com/photo/2023/06/23/19/34/campfire-8084064_1280.jpg'
  },
  {
    img: 'https://cdn.pixabay.com/photo/2023/04/26/03/48/drink-7951411_1280.jpg'
  },
  {
    img: 'https://cdn.pixabay.com/photo/2023/05/25/18/07/bird-8017963_1280.jpg'
  },
];

const aciveIndex = ref(0);


</script>

<template>
<div class="slider">
    <h2>image carousel slider</h2>
    
    <button class="prev" @click="aciveIndex--">prev</button>
    <button class="next" @click="aciveIndex++">next</button>


    <div class="items" v-for="(image, index) in images" :key="index">
      <img :src="image.img" alt="" v-show="aciveIndex==index">
    </div>
</div>
</template>

<style scoped>

.slider {
  position: relative;
}
.prev {
  position: absolute;
  top: 45%;
  left: -15%;
}
.next {
  position: absolute;
  top: 45%;
  right: -15%;
}


</style>
