<template>
  <section class="bg-[#31427A] text-white py-8 md:py-16">
    <div class="container mx-auto px-4">
      <!-- Title and Description -->
      <div class="w-full md:w-[80%] xl:w-[60%] mx-auto space-y-4 md:space-y-6 text-center mb-8 md:mb-12">
        <h2 class="text-2xl md:text-3xl lg:text-4xl font-bold leading-tight">
          Simple, Transparent Pricing
        </h2>
        <p class="text-sm md:text-base lg:text-lg">
          Our pricing plans are designed to suit traders of all levels, offering flexible options without hidden fees. Get access to premium features and expert tools that help you maximize your returns while minimizing costs.
        </p>
      </div>

      <!-- Toggle between Monthly and Yearly -->
      <div class="flex justify-center items-center mt-4 mb-8 space-x-4 relative">
        <span class="text-sm md:text-base">Pay Monthly</span>
        <label class="flex items-center cursor-pointer">
          <input type="checkbox" v-model="isYearly" class="hidden" />
          <div
            class="toggle-bg w-12 md:w-14 h-6 md:h-7 flex items-center bg-gray-500 rounded-full p-1"
          >
            <div class="dot w-5 md:w-6 h-5 md:h-6 bg-white rounded-full shadow-md"></div>
          </div>
        </label>
        <span class="text-sm md:text-base">Pay Yearly</span>
        <div class="hidden md:block absolute top-0 right-0 md:right-4 lg:right-8 xl:right-12">
          <img src="/src/components/icons/save25.svg" alt="Save 25%" class="w-12 h-12 md:w-16 md:h-16">
        </div>
      </div>

      <!-- Pricing Plans -->
      <div
        class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-4 gap-4 md:gap-6 w-full max-w-7xl mx-auto"
    ref="pricingCards"
      >
        <!-- Essential Plan -->
        <div
          ref="card0"
          class="pricing-card hover-effect bg-white bg-opacity-5 border border-white border-opacity-10 p-4 md:p-6 rounded-lg shadow-lg flex flex-col justify-between"
        >
          <div>
            <h3 class="text-lg md:text-xl text-left text-white font-semibold mb-2 md:mb-4">
              Essential
            </h3>
            <p class="text-white text-left text-sm md:text-base mb-4">
              Ideal for individuals who need quick access to basic features.
            </p>
            <div class="text-white mb-4 md:mb-6 flex items-end gap-2">
              <p class="text-3xl md:text-4xl lg:text-5xl text-left font-semibold">₹{{ isYearly ? '21000' : '2399' }}</p>
              <p class="text-white text-xs md:text-sm">+GST / {{ isYearly ? 'Year' : 'Month' }}</p>
            </div>
          </div>
          <div>
            <button
              class="w-full bg-transparent border-2 border-white text-white py-2 rounded-lg mb-4 md:mb-6 hover:bg-white hover:text-blue-800 text-sm md:text-base"
            >
              Get Started Now
            </button>
            <!-- Features List -->
            <ul class="space-y-2 md:space-y-4 text-white w-full">
              <li v-for="(feature, index) in essentialFeatures" :key="index" class="flex items-start gap-2 text-xs md:text-sm">
                <img :src="feature.included ? '/images/icons/right.svg' : '/images/icons/wrong.svg'" class="w-4 h-4 md:w-5 md:h-5 mt-0.5 flex-shrink-0" :alt="feature.included ? 'Included' : 'Not included'" />
                <span>{{ feature.text }}</span>
              </li>
            </ul>
          </div>
        </div>

        <!-- Evaluation Plan -->
        <div
          ref="card1"
          class="pricing-card bg-white bg-opacity-5 border border-white border-opacity-10 p-4 md:p-6 rounded-lg shadow-lg flex flex-col justify-between"
        >
          <div>
            <h3 class="text-lg md:text-xl text-left text-white font-semibold mb-2 md:mb-4">
              Evaluation
            </h3>
            <p class="text-white text-left text-sm md:text-base mb-4">
              Ideal for individuals who need advanced features for evaluation.
            </p>
            <div class="text-white mb-4 md:mb-6 flex items-end gap-2">
              <p class="text-3xl md:text-4xl lg:text-5xl text-left font-semibold">₹{{ isYearly ? '28000' : '3199' }}</p>
              <p class="text-white text-xs md:text-sm">+GST / {{ isYearly ? 'Year' : 'Month' }}</p>
            </div>
          </div>
          <div>
            <button
              class="w-full bg-transparent border-2 border-white text-white py-2 rounded-lg mb-4 md:mb-6 hover:bg-white hover:text-blue-800 text-sm md:text-base"
            >
              Get Started Now
            </button>
            <!-- Features List -->
            <ul class="space-y-2 md:space-y-4 text-white w-full">
              <li v-for="(feature, index) in evaluationFeatures" :key="index" class="flex items-start gap-2 text-xs md:text-sm">
                <img :src="feature.included ? '/images/icons/right.svg' : '/images/icons/wrong.svg'" class="w-4 h-4 md:w-5 md:h-5 mt-0.5 flex-shrink-0" :alt="feature.included ? 'Included' : 'Not included'" />
                <span>{{ feature.text }}</span>
              </li>
            </ul>
          </div>
        </div>

        <!-- Elite Plan -->
        <div 
          ref="card2"
          class="pricing-card bg-[#30AFE5] p-4 md:p-6 rounded-lg shadow-lg flex flex-col justify-between"
        >
          <div>
            <h3 class="text-lg md:text-xl font-semibold mb-2 md:mb-4 text-left">Elite</h3>
            <p class="text-white-300 mb-4 text-left text-sm md:text-base">
              Ideal for individuals who need advanced features and tools for
              professional trading.
            </p>
            <div class="mb-4 md:mb-6 flex items-end gap-2">
              <p class="text-3xl md:text-4xl lg:text-5xl text-left font-semibold">₹{{ isYearly ? '36000' : '4199' }}</p>
              <p class="text-xs md:text-sm">+GST / {{ isYearly ? 'Year' : 'Month' }}</p>
            </div>
          </div>
          <div>
            <button
              class="w-full bg-white text-blue-800 py-2 rounded-lg mb-4 md:mb-6 hover:bg-gray-100 text-sm md:text-base"
            >
              Get Started Now
            </button>
            <!-- Features List -->
            <ul class="space-y-2 md:space-y-4 w-full">
              <li v-for="(feature, index) in eliteFeatures" :key="index" class="flex items-start gap-2 text-xs md:text-sm">
                <img :src="feature.included ? '/images/icons/right.svg' : '/images/icons/wrong.svg'" class="w-4 h-4 md:w-5 md:h-5 mt-0.5 flex-shrink-0" :alt="feature.included ? 'Included' : 'Not included'" />
                <span>{{ feature.text }}</span>
              </li>
            </ul>
          </div>
        </div>

        <!-- HNI Plan -->
        <div
          ref="card3"
          class="pricing-card bg-white bg-opacity-5 border border-opacity-10 border-white p-4 md:p-6 rounded-lg shadow-lg flex flex-col justify-between"
        >
          <div>
            <h3 class="text-lg md:text-xl text-left text-white font-semibold mb-2 md:mb-4">
              HNI
            </h3>
            <p class="text-white text-left text-sm md:text-base mb-4">
              Ideal for high net-worth individuals who need personalized services and security for
              large-scale trading.
            </p>
            <div class="text-white mb-4 md:mb-6 flex items-end gap-2">
              <p class="text-3xl md:text-4xl lg:text-5xl text-left font-semibold">₹{{ isYearly ? '50000' : '5999' }}</p>
              <p class="text-white text-xs md:text-sm">+GST / {{ isYearly ? 'Year' : 'Month' }}</p>
            </div>
          </div>
          <div>
            <button
              class="w-full bg-transparent border-2 border-white text-white py-2 rounded-lg mb-4 md:mb-6 hover:bg-white hover:text-blue-800 text-sm md:text-base"
            >
              Get Started Now
            </button>
            <!-- Features List -->
            <ul class="space-y-2 md:space-y-4 text-white w-full">
              <li v-for="(feature, index) in hniFeatures" :key="index" class="flex items-start gap-2 text-xs md:text-sm">
                <img :src="feature.included ? '/images/icons/right.svg' : '/images/icons/wrong.svg'" class="w-4 h-4 md:w-5 md:h-5 mt-0.5 flex-shrink-0" :alt="feature.included ? 'Included' : 'Not included'" />
                <span>{{ feature.text }}</span>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { ref, onMounted } from 'vue';
import gsap from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

export default {
  name: "PricingSection",
  setup() {
    const isYearly = ref(false);
    const pricingCards = ref(null);
    const card0 = ref(null);
    const card1 = ref(null);
    const card2 = ref(null);
    const card3 = ref(null);

    const essentialFeatures = [
      { text: "1 YEAR ACCESS", included: true },
      { text: "NO HIDDEN CHARGES", included: true },
      { text: "NO OF DEPLOYMENT - 2", included: true },
      { text: "SEGMENT - 1 (N/B)", included: true },
      { text: "PAPERTRADING", included: true },
      { text: "CREATE YOUR STRATEGY", included: false },
      { text: "WEBHOOK FEATURE", included: false },
      { text: "MULTIPLE CLIENT MANAGEMENT", included: false },
    ];

    const evaluationFeatures = [
      { text: "1 YEAR ACCESS", included: true },
      { text: "NO HIDDEN CHARGES", included: true },
      { text: "NO OF DEPLOYMENT - 5", included: true },
      { text: "SEGMENT - ALL", included: true },
      { text: "PAPERTRADING", included: true },
      { text: "CREATE YOUR STRATEGY - 1", included: true },
      { text: "WEBHOOK FEATURE", included: false },
      { text: "MULTIPLE CLIENT MANAGEMENT", included: false },
    ];

    const eliteFeatures = [
      { text: "1 YEAR ACCESS", included: true },
      { text: "NO HIDDEN CHARGES", included: true },
      { text: "NO OF DEPLOYMENT - ALL", included: true },
      { text: "SEGMENT - ALL", included: true },
      { text: "PAPERTRADING", included: true },
      { text: "CREATE YOUR STRATEGY - 3", included: true },
      { text: "WEBHOOK FEATURE - 2", included: true },
      { text: "MULTIPLE CLIENT MANAGEMENT - 1", included: true },
    ];

    const hniFeatures = [
      { text: "1 YEAR ACCESS", included: true },
      { text: "NO HIDDEN CHARGES", included: true },
      { text: "NO OF DEPLOYMENT - ALL", included: true },
      { text: "SEGMENT - ALL", included: true },
      { text: "PAPERTRADING", included: true },
      { text: "CREATE YOUR STRATEGY - 3", included: true },
      { text: "WEBHOOK FEATURE - 5", included: true },
      { text: "MULTIPLE CLIENT MANAGEMENT - 2", included: true },
    ];

    onMounted(() => {
      const cards = [card0.value, card1.value, card2.value, card3.value];
      
      cards.forEach((card, index) => {
        gsap.set(card, { 
          opacity: 0, 
          y: () => {
            if (window.innerWidth <= 768) return 50;
            if (window.innerWidth <= 1279) return 75;
            return 100;
          }
        });

        ScrollTrigger.create({
          trigger: card,
          start: "top bottom-=100",
          onEnter: () => {
            gsap.to(card, {
              opacity: 1,
              y: 0,
              duration: () => {
                if (window.innerWidth <= 768) return 0.6;
                if (window.innerWidth <= 1279) return 0.7;
                return 0.8;
              },
              ease: "power3.out",
              
              delay: index * 0.2
            });
          },
          once: true
        });
      });
    });

    return {
      isYearly,
      pricingCards,
      card0,
      card1,
      card2,
      card3,
      essentialFeatures,
      evaluationFeatures,
      eliteFeatures,
      hniFeatures,
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

/* Pricing Card Animation Styles */
.pricing-card {
  opacity: 0;
  transform: translateY(100px);
}

@media (max-width: 768px) {
  .pricing-card {
    transform: translateY(50px);
  }
}

@media (min-width: 769px) and (max-width: 1279px) {
  .pricing-card {
    transform: translateY(75px);
  }
}


</style>