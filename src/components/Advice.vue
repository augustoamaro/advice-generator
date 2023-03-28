<template>
        <h1 class="advice-number">ADVICE #{{ adviceId }}</h1>
        <p class="advice">"{{ advice }}"</p>
        <img class="divider" src="../assets/pattern-divider-desktop.svg" alt="divider">
</template>
      
<script>
        export default {
          props: {
            adviceId: {
              type: Number,
              default: '',
            },
            advice: {
              type: String,
              default: '',
            },
          },
        };
</script>

<style>
        @import './styles/Advice.css';
</style>