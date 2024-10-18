<script setup>
import { RouterLink } from 'vue-router'
import { reactive, ref } from 'vue';

const form = reactive({
    name: '',
    email: '',
    mobile: '',
    message: '',
    agreeToTerms: false,
});

const handleSubmit = async () => {
  if (form.agreeToTerms) {
    console.log(form);
    // Add your form submission logic here
    const response = await fetch('/contact-us', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify(form),
    });
    console.log(response);
    showForm.value = false; // Close the modal after submission
  } else {
    alert('Please agree to the Terms and Privacy Policy');
  }
};

const showForm = ref(false);
const handleForm = () => {
  showForm.value = !showForm.value;
};

const scrollTo = (sectionId) => {
      const element = document.getElementById(sectionId);
      if (element) {
        const yOffset = -170; // Adjust this value to fine-tune the scroll position
        const y = element.getBoundingClientRect().top + window.pageYOffset + yOffset;
        window.scrollTo({top: y, behavior: 'smooth'});
      }
      if (sidebarOpen.value) {
        toggleSidebar();
      }
    };
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
      <div v-if="showForm"
    class="transition-all fixed inset-0 w-full h-screen bg-black bg-opacity-50 flex justify-center items-center overflow-hidden"
    style="z-index: 9999;">
    <div class="bg-[#1e2a4a] rounded-md my-10">
      <div class="w-full max-w-md p-8 rounded-lg shadow-lg bg-opacity-100 relative">
        <div class="text-center mb-8">
          <img src="/images/LOGOlight.svg" alt="Logo" class="w-16 h-16 mx-auto mb-4 scale-150 hidden lg:block xl:block md:block" />
          <h2 class="text-3xl font-bold text-white mb-2">Contact Us</h2>
          <p class="text-gray-300">Please fill out the form below to get in touch.</p>
        </div>
        <form @submit.prevent="handleSubmit" action="/submit" method="POST" class="space-y-6">
          <div>
            <input v-model="form.name" type="text" placeholder="Name" required
              class="w-full px-4 py-2 rounded bg-[#31427A] text-white placeholder-gray-300 focus:outline-none focus:ring-2 focus:ring-white" />
          </div>
          <div>
            <input v-model="form.email" type="email" placeholder="Email" required
              class="w-full px-4 py-2 rounded bg-[#31427A] text-white placeholder-gray-300 focus:outline-none focus:ring-2 focus:ring-white" />
          </div>
          <div>
            <input v-model="form.mobile" type="tel" placeholder="Mobile Number" required
              class="w-full px-4 py-2 rounded bg-[#31427A] text-white placeholder-gray-300 focus:outline-none focus:ring-2 focus:ring-white" />
          </div>
          <div>
            <textarea v-model="form.message" placeholder="Your Message" required rows="4"
              class="w-full px-4 py-2 rounded bg-[#31427A] text-white placeholder-gray-300 focus:outline-none focus:ring-2 focus:ring-white resize-none"></textarea>
          </div>
          <div class="flex items-center">
            <input type="checkbox" id="terms" v-model="form.agreeToTerms" required class="mr-2" />
            <label for="terms" class="text-gray-300 text-sm">I agree to the Terms and Privacy Policy.</label>
          </div>
          <div class="flex justify-between">
            <button type="submit"
              class="px-8 py-2 bg-white text-[#1e2a4a] font-semibold rounded hover:bg-gray-200 focus:outline-none focus:ring-2 focus:ring-white">
              Submit
            </button>
            <button @click="showForm = false"
              class="px-8 py-2 bg-gray-500 text-white font-semibold rounded hover:bg-gray-600 focus:outline-none focus:ring-2 focus:ring-gray-700">
              Close
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
      <div class="space-y-2 text-[16px] justify-self-start mt-8 md:mt-0 md:justify-self-center">
        <p>Quick Links</p>
        <div class="text-[#89A3B2] space-y-1">
          <a class="cursor-pointer hover:text-white block" href="https://app.futuremanagment.com/register">Register as a User</a>
          <a class="cursor-pointer hover:text-white block" href="https://app.futuremanagment.com/register">Sign in</a>
          
          
          <button @click="scrollTo('about')" class="cursor-pointer hover:text-white block">About Us</button>

          <button @click="handleForm" class="cursor-pointer hover:text-white block" >Contact Us</button>
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
        <p>All Rights Reserved</p>
      </div>
    </div>
  </footer>
</template>
