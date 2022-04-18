<template>
  <div class="pt-[52px] max-w-[456px] mx-auto">
    <img src="../assets/Progress1.svg" alt="Progress 1/3">
    <h1 class="pt-20 font-[Poppins] font-bold text-[32px] leading-[36px]">Registration</h1>
    <p class="pt-4">Fill in the registration data. It will take a couple of minutes. All you need is a phone number and e-mail</p>
    <div class="flex gap-4 bg-[#F0F2F4] h-[68px] mt-8 p-4 rounded-lg">
      <img src="../assets/Lock.svg" class="h-6" alt="">
      <p class="text-[13px] leading-[18px]">We take privacy issues seriously. You can be sure that your personal data is securely protected.</p>
      <img src="../assets/Cross.svg" class="h-6" alt="Close">
    </div>
      <div class="h-40 p-8 rounded-lg border-[1px] border-[#E2E4E5] mt-8">
        <p class="text-sm font-[Poppins]">Enter your phone number</p>
        <div class="flex mt-8 h-11 gap-4">
          <select name="countrynum" id="countrynum" class="font-[Roboto] text-lg pl-4 w-20 border-b-[1px] border-[#E2E4E5] appearance-none pr-6 bg-no-repeat bg-right" style="background-image: url('./src/assets/Arrow.svg');">
            <option value="+1">+1</option>
            <option value="+370">+370</option>
            <option value="+371">+371</option>
            <option value="+372">+372</option>
          </select>
          <input type="tel" name="phone" id="phone" class="font-[Roboto] text-lg flex-1 border-b-[1px] border-[#E2E4E5] px-4 py-2">
        </div>
      </div>
      <div class="h-[268px] p-8 rounded-lg border-[1px] border-[#E2E4E5] mt-8 flex flex-col">
        <p class="font-[Poppins] text-sm">Enter your email</p>
        <input type="email" name="email" id="email" class="font-[Roboto] text-lg mt-2 px-4 py-2 flex-1 border-b-[1px] border-[#E2E4E5]">
        <p class="font-[Poppins] text-sm mt-8">Set a password</p>
        <div class="flex mt-2 h-11 border-b-[1px] border-[#E2E4E5]">
          <input v-if="showPassword" type="text" class="font-[Roboto] text-lg px-4 py-2 flex-1" v-model="password">
          <input v-else v-model="password" type="password" name="password" id="password" class="px-4 py-2 flex-1">
          <button class="h-11 w-6 bg-center bg-no-repeat" @click="toggleShow" style="background-image: url('./src/assets/Eye.svg');"></button>
        </div>
        <div class="mt-2 flex invisible">
          <img src="../assets/Checkmark.svg" alt="">
          <p class="ml-1 text-[#34C759] font-[Poppins] text-xs">Good password</p>
        </div>
      </div>
      <input type="submit" value="Send Code" class="mt-8 py-3 px-6 border-[1px] border-[#BBBFC1] rounded w-[137px]">
  </div>
</template>

<script>
export default {
  data() {
    return {
      showPassword: false,
      password: null
    };
  },
  computed: {
    buttonLabel() {
      return (this.showPassword) ? "Hide" : "Show";
    }
  },
  methods: {
    toggleShow() {
      this.showPassword = !this.showPassword;
    }
  }
};
</script>