<script setup>
import { ref } from 'vue';

const price1 = ref(60)
const price2 = ref(70)
const menus = ['Home', 'Shop', 'About']
const products = ['역삼동원룸', '천호동원룸', '마포구원룸']
</script>

<template>
  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>

  <div v-for="product in products" :key="product">
    <h4>{{ product }}</h4>
    <p>50 만원</p>
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
