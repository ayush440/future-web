<script setup>
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
</script>

<template>
  <!-- Contact Form Modal -->
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

  <!-- Hero Section -->
  <section class="bg-[#1e2a4a] flex flex-col xl:flex-row items-center justify-between relative py-6">
    <div class="text-white w-full xl:w-[60%] space-y-4 md:space-y-8 p-8 md:p-10 xl:p-20">
      <h1 class="font-bold text-[43px] xl:text-[60px] leading-[60px] md:leading-[65px]">The Future of Trading is Here</h1>
      <p class="font-light text-[16px] md:text-[18px] w-[80%] md:w-[60%] xl:w-full">Our algorithmic trading software automates complex strategies, delivering speed and precision in every trade. Maximize profits, reduce risks, and stay ahead of the market with seamless, data-driven execution.</p>
      <button @click="handleForm" class="p-2 bg-white text-[#1e2a4a] font-bold rounded-[4px] w-[50%] md:w-[35%]">Get Started</button>
    </div>
    <div class="w-full mt-60 xl:w-[50%]">
      <img src="/images/hero/dashboard.png" alt="" class="absolute bottom-0 right-0 w-[350px] md:w-[450px] xl:w-[600px] 2xl:w-[600px] 3xl:max-w-[500px]">
    </div>
  </section>
</template>

<style scoped>
img {
  max-width: none;
  object-fit: contain;
}
</style>
