<template>
    <div class="h-40 p-8 rounded-lg border-[1px] border-[#E2E4E5] mt-8">
      <p class="text-sm font-[Poppins]">
        Enter your phone number
      </p>
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
</template>