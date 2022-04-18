<template>
    <div class="h-[268px] p-8 rounded-lg border-[1px] border-[#E2E4E5] mt-8 flex flex-col">
        <p class="font-[Poppins] text-sm">
            Enter your email
        </p>
        <input type="email" name="email" id="email" class="font-[Roboto] text-lg mt-2 px-4 py-2 flex-1 border-b-[1px] border-[#E2E4E5]">
        <p class="font-[Poppins] text-sm mt-8">
            Set a password
        </p>
        <div class="flex mt-2 h-11 border-b-[1px] border-[#E2E4E5]">
            <input v-if="showPassword" type="text" class="font-[Roboto] text-lg px-4 py-2 flex-1" v-model="password">
            <input v-else v-model="password" type="password" name="password" id="password" class="px-4 py-2 flex-1 tracking-[4px]">
            <button class="h-11 w-6 bg-center bg-no-repeat" @click="toggleShow" style="background-image: url('./src/assets/Eye.svg');">
            </button>
        </div>
        <div class="mt-2 flex invisible">
            <img src="../assets/Checkmark.svg" alt="">
            <p class="ml-1 text-[#34C759] font-[Poppins] text-xs">
                Good password
            </p>
        </div>
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