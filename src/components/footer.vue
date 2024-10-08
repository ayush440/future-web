<script setup>
import { RouterLink } from 'vue-router'
</script>

<template>
  <footer class="px-10 pt-10 md:pt-16 xl:px-20 pb-10 bg-[#31427a] text-white">
    <div class="grid grid-cols-1 md:grid-cols-3 xl:grid-cols-4 place-items-start justify-items-center 3xl:max-w-[85%] mx-auto">
      <div class="space-y-6 justify-self-start mt-8 md:mt-0 md:justify-self-center">
        <img src="/images/LOGOlight.svg" alt="Company Logo" />
        <p class="text-[#89A3B2] text-[16px]">
          Keep all your health records in one secure place for easy access to your medical history during doctor visits.
        </p>
      </div>
      <div class="space-y-2 text-[16px] justify-self-start mt-8 md:mt-0 md:justify-self-center">
        <p>Quick Links</p>
        <div class="text-[#89A3B2] space-y-1">
          <p>Register as a User</p>
          <p>Sign in</p>
          <RouterLink :to="{ path: '/', hash: '#about' }" class= "cursor-pointer hover:text-white">About Us</RouterLink>
          <p>Contact Us</p>
        </div>
      </div>
      <div class="space-y-2 text-[16px] justify-self-start mt-8 md:mt-0 md:justify-self-center">
        <p>Legal</p>
        <div class="text-[#89A3B2] space-y-1 flex flex-col">
          <RouterLink :to="{ path: '/terms-and-conditions', hash: '#disclaimer' }" class="cursor-pointer hover:text-white">Disclaimer</RouterLink>
          <RouterLink :to="{ path: '/terms-and-conditions', hash: '#privacy' }" class="cursor-pointer hover:text-white">Privacy Policy</RouterLink>
          <RouterLink :to="{ path: '/terms-and-conditions', hash: '#terms' }" class="cursor-pointer hover:text-white">Terms & Conditions</RouterLink>
        </div>
      </div>
      <div class="space-y-3 text-[16px] justify-self-start mt-8 xl:justify-self-center xl:mt-0">
        <p>Follow Us On</p>
        <div class="flex items-center gap-3">
          <i class="pi pi-linkedin text-[27px]"></i>
          <i class="pi pi-instagram text-[27px]"></i>
          <i class="pi pi-facebook text-[27px]"></i>
        </div>
      </div>
    </div>
    <div class="mt-16 md:mt-20 flex flex-col md:flex-row items-center justify-between 3xl:max-w-[85%] mx-auto">
      <div class="flex items-center gap-1">
        <p>Backed By</p>
        <a href="https://www.xtentioncrew.tech/" target="_blank">
          <img src="/images/xtentionLogo.svg" alt="Xtention Logo">
        </a>
      </div>
      <div class="text-[#89A3B2]">
        <!-- all rights -->
        <p>All Rights Reserved</p>  
      </div>
    </div>
  </footer>
</template>
