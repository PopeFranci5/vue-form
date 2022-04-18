<script setup>
import Privacy from '../components/Privacy.vue'
import EmailForm from '../components/EmailForm.vue'
import PhoneForm from '../components/PhoneForm.vue'
</script>

<template>
  <div class="pt-[52px] max-w-[456px] mx-auto">
    <img src="../assets/Progress1.svg" alt="Progress 1/3">
    <h1 class="pt-20 font-[Poppins] font-bold text-[32px] leading-[36px]">
      Registration
    </h1>
    <p class="pt-4 font-[Roboto] font-light text-[#575F6E]">
      Fill in the registration data. It will take a couple of minutes. All you need is a phone number and e-mail
    </p>
    <Privacy />
    <PhoneForm />
    <EmailForm />
    <input type="submit" value="Register Now" class="mt-8 py-3 px-8 bg-[#007AFF] rounded w-[169px] font-[Poppins] font-medium text-white">
  </div>
</template>
