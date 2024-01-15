<script setup>
import { ref } from 'vue';

const price1 = ref(60)
const price2 = ref(70)
const products = ['역삼동원룸', '천호동원룸', '마포구원룸']
</script>

<template>
  <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
  <div>
    <h4>{{ products[0] }}</h4>
    <p>50 만원</p>
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <p>70 만원</p>
  </div>
  <div>
    <h4>{{ products[2] }}</h4>
    <p>90 만원</p>
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
</style>
