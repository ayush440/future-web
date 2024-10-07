<template>
  <section class="bg-[#31427A] text-white py-16">
    <div class="container mx-auto">
      <!-- Title and Description -->
      <div class="w-[90%] md:w-[80%] xl:w-[50%] mx-auto space-y-6 text-center">
        <h2 class="text-3xl md:text-4xl font-bold leading-tight">
          Simple, Transparent Pricing
        </h2>
        <p class="text-base md:text-lg">
          Our pricing plans are designed to suit traders of all levels, offering flexible options without hidden fees. Get access to premium features and expert tools that help you maximize your returns while minimizing costs.
        </p>
      </div>

      <!-- Toggle between Monthly and Yearly -->
      <div class="flex justify-center items-center mt-8 mb-8 space-x-4 relative">
        <span>Pay Monthly</span>
        <label class="flex items-center cursor-pointer">
          <input type="checkbox" v-model="isYearly" class="hidden" />
          <div
            class="toggle-bg w-14 h-7 flex items-center bg-gray-500 rounded-full p-1"
          >
            <div class="dot w-6 h-6 bg-white rounded-full shadow-md"></div>
          </div>
        </label>
        <span>Pay Yearly</span>
        <div class="hidden md:block absolute top-2 right-0 md:top-0 md:right-[80px] xl:top-[-5px] xl:right-[350px] 2xl:right-[450px]">
          <img src="/src/components/icons/save25.svg" alt="Save 25%" class="w-16 h-16">
        </div>
      </div>

      <!-- Pricing Plans -->
      <div
        class="grid px-4 grid-cols-1 md:grid-cols-2 xl:grid-cols-4 w-full md:w-[65%] xl:w-[95%] 2xl:w-[85%] mx-auto gap-6 md:mt-20 xl:mt-16"
      >
        <!-- Freebie Plan -->
        <div
          class="bg-white bg-opacity-5 border border-white border-opacity-10 p-6 rounded-lg shadow-lg"
        >
          <h3 class="text-xl text-left text-white font-semibold mb-4">
            Freebie
          </h3>
          <p class="text-white text-left mb-4">
            Ideal for individuals who need quick access to basic features.
          </p>
          <div class="text-white mb-6 flex items-center gap-4">
            <p class="text-[56px] text-left font-semibold">$0</p>
            <p class="text-white text-[16px]">/ {{ isYearly ? 'Year' : 'Month' }}</p>
          </div>
          <button
            class="w-full bg-transparent border-2 border-white text-white py-2 rounded-lg mb-6 hover:bg-white hover:text-blue-800"
          >
            Get Started Now
          </button>
          <!-- Features List -->
          <ul class="space-y-4 text-white w-full md:mx-0 lg:mx-0 sm:mx-0">
            <li v-for="(feature, index) in freebieFeatures" :key="index" class="flex items-start gap-2 text-[16px]">
              <img :src="feature.included ? '/images/icons/right.svg' : '/images/icons/wrong.svg'" class="w-5 h-5 mt-0.5 flex-shrink-0" :alt="feature.included ? 'Included' : 'Not included'" />
              <span>{{ feature.text }}</span>
            </li>
          </ul>
        </div>

        <!-- Additional Freebie Plan (Exact copy of the first one) -->
        <div
          class="bg-white bg-opacity-5 border border-white border-opacity-10 p-6 rounded-lg shadow-lg"
        >
          <h3 class="text-xl text-left text-white font-semibold mb-4">
            Freebie
          </h3>
          <p class="text-white text-left mb-4">
            Ideal for individuals who need quick access to basic features.
          </p>
          <div class="text-white mb-6 flex items-center gap-4">
            <p class="text-[56px] text-left font-semibold">$0</p>
            <p class="text-white text-[16px]">/ {{ isYearly ? 'Year' : 'Month' }}</p>
          </div>
          <button
            class="w-full bg-transparent border-2 border-white text-white py-2 rounded-lg mb-6 hover:bg-white hover:text-blue-800"
          >
            Get Started Now
          </button>
          <!-- Features List -->
          <ul class="space-y-4 text-white w-full md:mx-0 lg:mx-0 sm:mx-0">
            <li v-for="(feature, index) in freebieFeatures" :key="index" class="flex items-start gap-2 text-[16px]">
              <img :src="feature.included ? '/images/icons/right.svg' : '/images/icons/wrong.svg'" class="w-5 h-5 mt-0.5 flex-shrink-0" :alt="feature.included ? 'Included' : 'Not included'" />
              <span>{{ feature.text }}</span>
            </li>
          </ul>
        </div>

        <!-- Professional Plan -->
        <div class="bg-[#30AFE5] p-6 rounded-lg shadow-lg">
          <h3 class="text-xl font-semibold mb-4 text-left">Professional</h3>
          <p class="text-white-300 mb-4 text-left">
            Ideal for individuals who need advanced features and tools for
            client work.
          </p>
          <div class="mb-6 flex items-center gap-4">
            <p class="text-[56px] text-left font-semibold">${{ isYearly ? '250' : '25' }}</p>
            <p class="text-[16px]">/ {{ isYearly ? 'Year' : 'Month' }}</p>
          </div>
          <button
            class="w-full bg-white text-blue-800 py-2 rounded-lg mb-6 hover:bg-gray-100"
          >
            Get Started Now
          </button>
          <!-- Features List -->
          <ul class="space-y-4 w-full md:mx-0 lg:mx-0 sm:mx-0">
            <li v-for="(feature, index) in professionalFeatures" :key="index" class="flex items-start gap-2 text-[16px]">
              <img :src="feature.included ? '/images/icons/right.svg' : '/images/icons/wrong.svg'" class="w-5 h-5 mt-0.5 flex-shrink-0" :alt="feature.included ? 'Included' : 'Not included'" />
              <span>{{ feature.text }}</span>
            </li>
          </ul>
        </div>

        <!-- Enterprise Plan -->
        <div
          class="bg-white bg-opacity-5 border border-opacity-10 border-white p-6 rounded-lg shadow-lg"
        >
          <h3 class="text-xl text-left text-white font-semibold mb-4">
            Enterprise
          </h3>
          <p class="text-white text-left mb-4">
            Ideal for businesses who need personalized services and security for
            large teams.
          </p>
          <div class="text-white mb-6 flex items-center gap-4">
            <p class="text-[56px] text-left font-semibold">${{ isYearly ? '1000' : '100' }}</p>
            <p class="text-[#4B5768] text-[16px]">/ {{ isYearly ? 'Year' : 'Month' }}</p>
          </div>
          <button
            class="w-full bg-transparent border-2 border-white text-white py-2 rounded-lg mb-6 hover:bg-white hover:text-blue-800"
          >
            Get Started Now
          </button>
          <!-- Features List -->
          <ul class="space-y-4 text-white w-full md:mx-0 lg:mx-0 sm:mx-0">
            <li v-for="(feature, index) in enterpriseFeatures" :key="index" class="flex items-start gap-2 text-[16px]">
              <img :src="feature.included ? '/images/icons/right.svg' : '/images/icons/wrong.svg'" class="w-5 h-5 mt-0.5 flex-shrink-0" :alt="feature.included ? 'Included' : 'Not included'" />
              <span>{{ feature.text }}</span>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "PricingSection",
  data() {
    return {
      isYearly: false,
      freebieFeatures: [
        { text: "20,000+ of PNG & SVG graphics", included: true },
        { text: "Access to 100 million stock images", included: true },
        { text: "Upload custom icons and fonts", included: false },
        { text: "Unlimited Sharing", included: false },
        { text: "Upload graphics & video in up to 4k", included: false },
        { text: "Unlimited Projects", included: false },
        { text: "Instant Access to our design system", included: false },
        { text: "Create teams to collaborate on designs", included: false },
      ],
      professionalFeatures: [
        { text: "20,000+ of PNG & SVG graphics", included: true },
        { text: "Access to 100 million stock images", included: true },
        { text: "Upload custom icons and fonts", included: true },
        { text: "Unlimited Sharing", included: true },
        { text: "Upload graphics & video in up to 4k", included: true },
        { text: "Unlimited Projects", included: true },
        { text: "Instant Access to our design system", included: false },
        { text: "Create teams to collaborate on designs", included: false },
      ],
      enterpriseFeatures: [
        { text: "20,000+ of PNG & SVG graphics", included: true },
        { text: "Access to 100 million stock images", included: true },
        { text: "Upload custom icons and fonts", included: true },
        { text: "Unlimited Sharing", included: true },
        { text: "Upload graphics & video in up to 4k", included: true },
        { text: "Unlimited Projects", included: true },
        { text: "Instant Access to our design system", included: true },
        { text: "Create teams to collaborate on designs", included: true },
      ],
    };
  },
};
</script>

<style scoped>
/* Toggle Switch Styles */
.toggle-bg {
  transition: background-color 0.3s ease;
}
.dot {
  transition: transform 0.3s ease;
}
input:checked + .toggle-bg {
  background-color: #30afe5;
  border: 0.2px solid grey;
}
input:checked + .toggle-bg .dot {
  transform: translateX(100%);
}
</style>