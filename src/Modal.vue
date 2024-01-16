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
</template>

<script setup>
</script>

<style>
</style>