<script setup>
import logo from '@/assets/images/logo.svg';
</script>

<template>
  <section class="max-w-md w-full">
    <!-- Top section -->
    <div class="flex items-center justify-between bg-primary p-6 rounded-2xl">
      <!-- balance info -->
      <div>
        <span class="text-white">My balance</span>
        <h2 class="text-3xl font-semibold text-white mt-2">$921.48</h2>
      </div>
      <!-- logo -->
      <div>
        <img class="w-15" :src="logo" alt="logo" />
      </div>
    </div>

    <!-- Bottom section -->
    <div class="mt-5 bg-white p-6 rounded-2xl">
      <h3 class="text-2xl font-bold text-brown-1">Spending - Last 7 days</h3>
      <!-- chart -->
      <div
        class="grid grid-cols-7 gap-4 py-7 mt-6 border-b-2 border-b-red-100 h-55"
      >
        <div class="text-center flex flex-col justify-end h-full">
          <div class="w-full h-[30%] bg-primary rounded-lg"></div>
          <span class="text-gray-400 text-sm mt-2">mon</span>
        </div>
        <div class="text-center flex flex-col justify-end h-full">
          <div class="w-full h-[50%] bg-primary rounded-lg"></div>
          <span class="text-gray-400 text-sm mt-2">tue</span>
        </div>
        <div class="text-center flex flex-col justify-end h-full">
          <div class="w-full h-[100%] bg-secondary rounded-lg"></div>
          <span class="text-gray-400 text-sm mt-2">wed</span>
        </div>
        <div class="text-center flex flex-col justify-end h-full">
          <div class="w-full h-[40%] bg-primary rounded-lg"></div>
          <span class="text-gray-400 text-sm mt-2">thu</span>
        </div>
        <div class="text-center flex flex-col justify-end h-full">
          <div class="w-full h-[30%] bg-primary rounded-lg"></div>
          <span class="text-gray-400 text-sm mt-2">fri</span>
        </div>
        <div class="text-center flex flex-col justify-end h-full">
          <div class="w-full h-[70%] bg-primary rounded-lg"></div>
          <span class="text-gray-400 text-sm mt-2">sat</span>
        </div>
        <div class="text-center flex flex-col justify-end h-full">
          <div class="w-full h-[60%] bg-primary rounded-lg"></div>
          <span class="text-gray-400 text-sm mt-2">sun</span>
        </div>
      </div>

      <!-- Total info -->
      <div class="flex items-end justify-between pt-6">
        <div class="flex flex-col">
          <span class="text-gray-400">Total this month</span>
          <span class="text-5xl mt-1 font-bold text-brown-1">$478.33</span>
        </div>
        <div class="flex flex-col text-end">
          <span class="font-bold text-brown-1">+2.4%</span>
          <span class="text-gray-400">from last month</span>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
