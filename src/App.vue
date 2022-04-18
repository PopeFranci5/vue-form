<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
<div class="flex">
  <div class="flex mt-11 ml-[88px]">
    <img src="./assets/CompanyLogo.svg" alt="">
    <p class="font-[Raleway] font-bold text-[16px] leading-[18px]">COMPANY NAME</p>
  </div>
</div>
  <RouterView />
</template>
