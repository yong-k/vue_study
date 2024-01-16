<script setup>
import { ref } from 'vue';
import { oneroomDatas } from './assets/oneroom.js'

const onerooms = oneroomDatas
const menus = ['Home', 'Shop', 'About']
const clickedRoomNumber = ref(0)
const isModalOpen = ref(false)
</script>

<template>
  <div class="black-bg" v-if="isModalOpen">
    <div class="white-bg">
      <h4>{{ onerooms[clickedRoomNumber].title }}</h4>
      <img :src="onerooms[clickedRoomNumber].image" style="width:100%">
      <p>가격: {{ onerooms[clickedRoomNumber].price }} 원</p>
      <p>{{ onerooms[clickedRoomNumber].content }}</p>
      <button @click="isModalOpen = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>

  <div v-for="(oneroom, i) in onerooms" :key="i">
    <img :src="oneroom.image" class="room-img">
    <h4 @click="isModalOpen = true; clickedRoomNumber = i">{{ oneroom.title }}</h4>
    <p>{{ oneroom.price }} 원</p>
  </div>
</template>

<style scoped>
body {
  margin: 0
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
