<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios';

const advice = ref('');
const adviceNumber = ref('');

onMounted(async () => {
        try {
                const response = await axios.get('https://api.adviceslip.com/advice');
                adviceNumber.value = response.data.slip.id;
                advice.value = response.data.slip.advice;

        } catch (error) {
                console.log('Error fetching advice', error);
        }
});
</script>

<template>
        <h1 class="advice-number">ADVICE #{{ adviceNumber }}</h1>
        <p class="advice">"{{ advice }}"</p>
        <img class="divider" src="../assets/pattern-divider-desktop.svg" alt="divider">
        <div @click="getNewAdvice" class="circle">
                <img src="../assets/icon-dice.svg" alt="dice">
        </div>
</template>

<style>
.advice-number {
     font-family: 'Manrope';
     font-size: 13px;
     line-height: 18px;
     text-align: center;
     letter-spacing: 4.08571px;
     color: #53FFAA;
}

.advice {
        font-family: 'Manrope';
        font-size: 28px;
        line-height: 38px;
        text-align: center;
        letter-spacing: -0.3px;
        color: #CEE3E9;
        padding-bottom: 40px;
}

.circle {
    width: 64px;
    height: 64px;
    background-color: #53FFAA;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    top: 395px;
}

.circle:hover {
  background: #53FFAA;
  box-shadow: 0px 0px 40px #53FFAA;
  cursor: pointer;
}

.circle img {
  width: 24px;
  height: 24px;
}
</style>