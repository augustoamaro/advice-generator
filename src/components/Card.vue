<template>
  <div class="card">
    <Advice :advice="advice" :adviceId="adviceId" />
    <div @click="getNewAdvice" class="circle">
      <img src="../assets/icon-dice.svg" alt="dice">
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios';
import Advice from './Advice.vue';

const adviceId = ref(0);
const advice = ref('');

async function getNewAdvice() {
  try {
    const response = await axios.get('https://api.adviceslip.com/advice');
    adviceId.value = response.data.slip.id;
    advice.value = response.data.slip.advice;
  } catch (error) {
    console.error('Error fetching advice:', error);
  }
};

onMounted(getNewAdvice);
</script>

<style scoped>
  @import './styles/Card.css';
</style>

