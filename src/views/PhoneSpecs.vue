<script setup>

import axios from 'axios'
import { reactive, watch } from 'vue';

const state = reactive({
    data: {}
})

const data = axios.get('https://api-mobilespecs.azharimm.site/v2/' + window.location.href.split("/").pop())
    .then(response => state.data = response.data)

</script>

<template>
    <h1>{{state.data.data.phone_name}}</h1>
    <div class="flex gap-4">
        <div
        v-for="(item, index) in state.data.data.phone_images"
        :key="index">
            <img :src=item alt="" class="max-h-64">
        </div>
    </div>
    <p><b>Release date:</b> {{state.data.data.release_date}}</p>
    <p><b>Dimensions:</b> {{state.data.data.dimension}}</p>
    <p><b>Operating system:</b> {{state.data.data.os}}</p>
    <p><b>Storage:</b> {{state.data.data.storage}}</p>
    <div class="text-center"
    v-for="(item, index) in state.data.data.specifications"
    :key="index">
        <h2 class="font-bold bg-gray-200 py-4">{{item.title}}</h2>
        <div
        v-for="(item, index) in item.specs">
            <h3 class="font-semibold bg-gray-100 py-1">{{item.key}}</h3>
            <div
            v-for="(item, index) in item.val">
                <p>{{item}}</p>
            </div>
        </div>
    </div>
</template>