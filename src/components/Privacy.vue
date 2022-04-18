<template>
    <div v-if="!isHidden" class="flex gap-4 bg-[#F0F2F4] h-[68px] mt-8 p-4 rounded-lg">
        <img src="../assets/Lock.svg" class="h-6" alt="">
        <p class="font-[Poppins] text-[13px] leading-[18px] w-[344px]">We take privacy issues seriously. You can be sure that your personal data is securely protected.</p>
        <button @click="isHidden = !isHidden" class="h-6">
            <img src="../assets/Cross.svg" alt="Close">
        </button>
    </div>
</template>

<script>
export default {
  data() {
    return {
      isHidden: false
    }
  }
}
</script>  