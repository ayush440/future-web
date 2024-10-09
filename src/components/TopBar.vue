<script setup>
import { ref, reactive } from 'vue';

// Sidebar open state
const sidebarOpen = ref(false);

// Toggle sidebar
const toggleSidebar = () => {
  sidebarOpen.value = !sidebarOpen.value;
};

// Contact form state and functions
const showContactForm = ref(false);
const form = reactive({
    name: '',
    email: '',
    mobile: '',
    message: '',
    agreeToTerms: false,
})

const handleContactForm = () => {
  showContactForm.value = !showContactForm.value;
}

const handleSubmit = async () => {
  if (form.agreeToTerms) {
    console.log(form)
    // Add your form submission logic here
    const response = await fetch('/contact-us', {
      method: 'POST',
      headers: {
        'Content-Type': 'application/json',
      },
      body: JSON.stringify(form),
    });
    console.log(response)
    showContactForm.value = false; // Close the modal after submission
  } else {
    alert('Please agree to the Terms and Privacy Policy');
  }
}
</script>

<template>
  <div class="flex justify-between items-center py-4 px-6 sticky top-0 z-30 bg-white border-b pb-1">
    <div class="flex items-center space-x-2">
      <img 
        src="/images/LOGOO.png" 
        alt="Future Management Services Logo" 
        class="w-auto h-12 md:h-16 lg:h-20 xl:h-24 scale-75"
      >
    </div>

    <!-- Links for desktop screens -->
    <div class="hidden lg:flex justify-center items-center gap-8">
      <div class="flex space-x-6 text-black font-semibold">
        <a href="#" class="hover:text-gray-400">Home</a>
        <a href="#about" class="hover:text-gray-400">About</a>
        <a href="#" @click.prevent="handleContactForm" class="hover:text-gray-400">Contact</a>
        <a href="#pricing" class="hover:text-gray-400">Pricing</a>
      </div>
      <button class="bg-primary hover:bg-blue-800 text-white px-4 py-2 rounded">
        <a href="https://app.futuremanagment.com/">Login/Signup</a>
      </button>
    </div>

    <!-- Burger menu button for mobile and tablet screens -->
    <button
      class="lg:hidden block text-primary focus:outline-none"
      @click="toggleSidebar"
    >
      <svg
        class="w-8 h-8"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M4 6h16M4 12h16m-7 6h7"
        ></path>
      </svg>
    </button>

    <!-- Sidebar for mobile screens -->
    <div
      class="fixed top-0 z-10 right-0 h-full w-64 bg-white shadow-lg transform transition-transform duration-300"
      :class="{'translate-x-full': !sidebarOpen, 'translate-x-0': sidebarOpen}"
    >
      <div class="flex justify-between items-center py-4 px-6 bg-primary text-white">
        <h1 class="text-xl font-bold">Menu</h1>
        <button class="focus:outline-none" @click="toggleSidebar">
          <svg
            class="w-6 h-6"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            ></path>
          </svg>
        </button>
      </div>
      <div class="flex flex-col space-y-4 px-6 mt-4 text-primary">
        <a href="#" class="hover:text-gray-400">Home</a>
        <a href="#about" class="hover:text-gray-400">About</a>
        <a href="#" @click.prevent="handleContactForm" class="hover:text-gray-400">Contact</a>
        <a href="#pricing" class="hover:text-gray-400">Pricing</a>
        <button class="bg-primary hover:bg-blue-800 text-white px-4 py-2 rounded">
          <a href="https://app.futuremanagment.com/">Login/Signup</a>
        </button>
      </div>
    </div>
  </div>

  <!-- Contact Form Modal -->
  <div v-if="showContactForm"
    class="transition-all z-50 fixed inset-0 w-full h-screen bg-black bg-opacity-50 flex justify-center items-center overflow-hidden">
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
              class="px-8 py-2 bg-white text-[#1e2a4a] font-semibold rounded hover:bg-white focus:outline-none focus:ring-2 focus:ring-yellow-700">
              Submit
            </button>
            <button @click="showContactForm = false"
              class="px-8 py-2 bg-gray-500 text-white font-semibold rounded hover:bg-gray-600 focus:outline-none focus:ring-2 focus:ring-gray-700">
              Close
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
img {
  max-width: none;
  object-fit: contain;
}
</style>