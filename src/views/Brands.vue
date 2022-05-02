<script setup>

import axios from 'axios'
import { reactive } from 'vue';

const state = reactive({
    data: {}
})

const data = axios.get('https://api-mobilespecs.azharimm.site/v2/brands')
    .then(response => state.data = response.data)

</script>

<template>
<div class="grid grid-cols-5 gap-3 justify-items-center">
    <div 
    v-for="(item, index) in state.data.data" 
    :key="index"
    class="text-center border-2 rounded-xl p-4 w-[90%]">
        <h2>{{ item.brand_name }}</h2>
        <p>Amount of phones: {{ item.device_count }}</p>
        <RouterLink :to="'/brands/' + item.brand_slug" class="bg-blue-400 rounded p-1">See their phones</RouterLink>
    </div>
</div>
</template>