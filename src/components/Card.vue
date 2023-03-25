<script setup>
import Advice from './Advice.vue';
</script>

<template>
  <div class="card">
      <Advice />
      <img class="divider" src="../assets/pattern-divider-desktop.svg" alt="divider">
      <div class="circle">
        <img src="../assets/icon-dice.svg" alt="dice">
      </div>
    </div>
  

</template>

<style scoped>
.card {
    width: 540px;
    height: 364px;
    background-color: #313A48;
    border-radius: 15px;
    box-shadow: 30px 50px 80px rgba(0, 0, 0, 0.100202);
    display: flex;
    justify-content: end;
    align-items: center;
    flex-direction: column;
    position: relative;
}

.divider {
    width: 444px;
    height: 16px;
    margin-bottom: 40px;
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
