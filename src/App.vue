<script setup>
import { ref } from 'vue';

const menus = ['Home', 'Shop', 'About']
const products = ['역삼동원룸', '천호동원룸', '마포구원룸']
const prices = [50, 70, 90]
const reports = ref([0, 0, 0])

function increase(idx) {
  this.reports[idx]++
}
</script>

<template>
  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>

  <div v-for="(product, i) in products" :key="i">
    <h4>{{ product }}</h4>
    <p>{{ prices[i] }} 만원</p>
    <button @click="increase(i)">허위매물신고</button> <span>신고수: {{ reports[i] }}</span>
  </div>
</template>

<style scoped>
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
</style>
