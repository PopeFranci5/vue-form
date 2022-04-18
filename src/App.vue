<script setup>
import { RouterLink, RouterView } from 'vue-router'
import CompanyName from './components/CompanyName.vue'
</script>

<template>
<div class="flex">
  <CompanyName />
  <RouterView />
</div>
  
</template>
