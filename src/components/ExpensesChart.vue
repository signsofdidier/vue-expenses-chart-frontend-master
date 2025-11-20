<script setup>
import logo from '@/assets/images/logo.svg';
import data from '../../data.json';

const totalAmount = data.reduce((acc, curr) => acc + curr.amount, 0);

const highestAmount = Math.max(...data.map((item) => item.amount));

const barStyles = data.map((item) => ({
  height: `${Math.floor((item.amount / highestAmount) * 100)}%`,
}));
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
    <div class="mt-5 bg-white/80 p-6 rounded-2xl">
      <h3 class="text-2xl font-bold text-brown-1">Spending - Last 7 days</h3>
      <!-- chart -->
      <div
        class="grid grid-cols-7 gap-4 py-7 mt-6 border-b-2 border-b-red-100 h-70"
      >
        <div
          v-for="(expense, index) in data"
          :key="index"
          class="text-center flex flex-col justify-end h-full relative group"
        >
          <div
            class="w-full rounded-lg group-hover:bg-secondary/70 transition duration-200 ease-in-out relative"
            :class="
              expense.amount === highestAmount ? 'bg-secondary' : 'bg-primary'
            "
            :style="barStyles[index]"
          >
            <!-- hover div -->
            <div
              class="bg-brown-1 px-2 py-1.5 rounded absolute top-0 left-1/2 -translate-x-1/2 -translate-y-11 opacity-0 group-hover:opacity-100 transition-all duration-200 ease-in-out"
            >
              <span class="text-white font-bold text-sm"
                >${{ expense.amount }}</span
              >
            </div>
          </div>
          <span class="text-gray-400 text-sm mt-2">{{ expense.day }}</span>
        </div>
      </div>

      <!-- Total info -->
      <div class="flex items-end justify-between pt-6 mb-4">
        <div class="flex flex-col">
          <span class="text-gray-400">Total this month</span>
          <span class="text-5xl mt-1 font-bold text-brown-1"
            >${{ totalAmount.toFixed(2) }}</span
          >
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
