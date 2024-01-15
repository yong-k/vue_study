<script setup>
import { ref } from 'vue';

const menus = ['Home', 'Shop', 'About']
const products = ['역삼동원룸', '천호동원룸', '마포구원룸']
const prices = [50, 70, 90]
const reports = ref([0, 0, 0])
const isModalOpen = ref(false)

function increase(idx) {
  this.reports[idx]++
}
</script>

<template>
  <div class="black-bg" v-if="isModalOpen">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <p>상세페이지 내용</p>
      <button @click="isModalOpen = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>

  <div v-for="(product, i) in products" :key="i">
    <img :src="`/img/room${i}.jpg`" class="room-img">
    <h4 @click="isModalOpen = true">{{ product }}</h4>
    <p>{{ prices[i] }} 만원</p>
    <button @click="increase(i)">허위매물신고</button> <span>신고수: {{ reports[i] }}</span>
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
