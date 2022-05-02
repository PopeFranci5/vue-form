<script setup>

import axios from 'axios'
import { reactive, watch } from 'vue';

const state = reactive({
    data: {},
    pagenumber: 1
})

const pagepath = window.location.pathname

const data = () => {
    axios.get('https://api-mobilespecs.azharimm.site/v2' + pagepath + '?page=' + state.pagenumber)
    .then(response => state.data = response.data)
}

data()

</script>

<template>
<div class="flex gap-4 mb-4">
    <div 
    v-for="(n, index) in state.data.data.last_page"
    :key="index">
        <button @click="state.pagenumber = n" class="border-2 w-8 h-8 text-center">
            {{n}}
        </button>
    </div>
</div>
<div class="grid grid-cols-3 gap-3 justify-items-center">
    <div 
    v-for="(item, index) in state.data.data.phones" 
    :key="index"
    class="text-center border-2 rounded-xl p-4 w-[90%]">
        <h2>{{ item.phone_name }}</h2>
        <img :src="item.image" alt="">
        <RouterLink :to="pagepath + '/' + item.slug">See phone specs</RouterLink>
    </div>
</div>
</template>

<script>

export default {
    data() {
        return {
            data: {},
            pagenumber: 1,
        }
    },
    mounted() {
        axios
            .get('https://api-mobilespecs.azharimm.site/v2' + window.location.pathname + '?page=' + this.pagenumber)
            .then(response => (this.data = response.data))
            .catch(error => {
                console.log(error)
            })
    },
    watch: {
        data: function(newValue) {
            this.apiChange()
        }
    },
    methods: {
        apiChange() {
            // axios
            // .get('https://api-mobilespecs.azharimm.site/v2' + window.location.pathname + '?page=' + this.pagenumber)
            // .then(response => this.data = response.data)
        }
    }
}

</script>