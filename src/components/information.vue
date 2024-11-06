<script setup>
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'

// Set up ref array to hold the number elements
const countRefs = ref([])

// Define the boxes with start and end values, suffixes, and descriptions
const boxes = [
  { startValue: 0, endValue: 1000, suffix: '+', description: 'Successful Trades Executed Daily', decimals: 0 },
  { startValue: 0, endValue: 500, suffix: '+', description: 'Satisfied Clients Worldwide', decimals: 0 },
  { startValue: 0, endValue: 5, suffix: '+', description: 'Years of Combined Financial and Tech Expertise', decimals: 0 },
  { startValue: 0, endValue: 99.9, suffix: '%', description: 'System Uptime for Continuous Trading', decimals: 1 },
]

// Run the animation on component mount
onMounted(() => {
  countRefs.value.forEach((el, index) => {
    const box = boxes[index]
    gsap.to(el, {
      innerHTML: box.endValue,
      duration: 3,
      ease: 'power1.out',
      onUpdate: function () {
        el.innerHTML = parseFloat(this.targets()[0].innerHTML).toFixed(box.decimals)
      },
    })
  })
})
</script>

<template>
  <section id="about-us" class="p-10 md:p-16 xl:p-20 3xl:max-w-[80%] mx-auto">
    <div class="w-full xl:w-[100%] space-y-3 ">
      <p class="text-[#31427A] font-bold text-[46px] text-center">About Us</p>
      <h1 class=" text-[30px] md:text-[36px] leading-[40px] md:leading-[45px] text-center">
        At <strong>Future Management Services</strong>, we’re on a mission to simplify and empower your trading experience with technology.
      </h1>
      <p class="text-[#667085] text-[16px] md:text-[20px] text-center">
        Our advanced algorithm trading web app connects seamlessly to multiple brokers, providing you with the tools to automate your trading in equity, commodities, futures, and options markets. With a range of pre-built trading strategies designed for various market conditions, we cater to both small and large investors, helping everyone make the most of their investments.
      </p>
      <p class="text-[#667085] text-[16px] md:text-[20px] text-center">
        In today’s fast-paced world, we understand that live trading isn’t always feasible. That’s why our platform lets you trade efficiently and effectively, without the need for constant monitoring. Simply connect your broker account to our app, select a strategy that fits your goals, and let our algorithms do the rest. With <strong>Future Management Services</strong>, you’ll never miss out on trading opportunities again, freeing you to focus on what truly matters. Start trading smarter, not harder, and let your investments work for you around the clock!
      </p>
    </div>

    <!-- Counting Animation Section -->
    <div class="mt-16 flex flex-col xl:flex-row space-y-8 xl:space-y-0 items-center justify-between gap-10">
      <div class="grid grid-cols-1 md:grid-cols-4 gap-6">
        <div class="flex flex-col items-center">
          <p class="text-[#31427A] font-semibold text-[60px]">
            <span :ref="el => { if (el) countRefs[0] = el }">0</span>+
          </p>
          <p class="font-bold text-[16px] text-center w-[50%]">Successful Trades Executed Daily</p>
        </div>
        <div class="flex flex-col items-center">
          <p class="text-[#31427A] font-semibold text-[60px]">
            <span :ref="el => { if (el) countRefs[1] = el }">0</span>+
          </p>
          <p class="font-bold text-[16px] text-center w-[50%]">Satisfied Clients Worldwide</p>
        </div>
        <div class="flex flex-col items-center">
          <p class="text-[#31427A] font-semibold text-[60px]">
            <span :ref="el => { if (el) countRefs[2] = el }">0</span>+
          </p>
          <p class="font-bold text-[16px] text-center w-[70%]">Years of Combined Financial and Tech Expertise</p>
        </div>
        <div class="flex flex-col items-center">
          <p class="text-[#31427A] font-semibold text-[60px]">
            <span :ref="el => { if (el) countRefs[3] = el }">0</span>%
          </p>
          <p class="font-bold text-[16px] text-center w-[50%]">System Uptime for Continuous Trading</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
/* Add any additional styles here if needed */
</style>
