<template>
  <div class="detail-content">
    <h2>Bootstrap 5 Stand-Alone Components Integrated with Vue 3</h2>
    <div class="logo-block">
      <img src="https://getbootstrap.com/docs/5.3/assets/brand/bootstrap-logo-shadow.png" alt="">
      <span>+</span>
      <img src="https://vuejs.org/logo.svg" alt="">
    </div>

    <div class="modal-block">
      <h4>Calling bootstrap modal with vue</h4>
      <Demo />
    </div>
  </div>

</template>

<script setup>

import Demo from './Demo.vue';

</script>