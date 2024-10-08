<template>
  <div class="terms-container">
    <header class="flex justify-between items-center py-4 px-6 sticky top-0 z-30 bg-white border-b">
      <div class="flex items-center space-x-2">
        <router-link to="/" class="logo-link">
          <img 
            src="/images/LOGOO.png" 
            alt="Future Management Services Logo" 
            class="w-auto h-12 md:h-16 lg:h-20 xl:h-24"
          >
        </router-link>
      </div>

      <!-- Links for desktop screens -->
      <div class="hidden lg:flex justify-center items-center gap-8">
        <div class="flex space-x-6 text-black font-semibold">
          <button @click="scrollTo('disclaimer')" class="hover:text-gray-400">Disclaimer</button>
          <button @click="scrollTo('privacy')" class="hover:text-gray-400">Privacy Policy</button>
          <button @click="scrollTo('terms')" class="hover:text-gray-400">Terms & Conditions</button>
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
          <button @click="scrollTo('disclaimer')" class="hover:text-gray-400">Disclaimer</button>
          <button @click="scrollTo('privacy')" class="hover:text-gray-400">Privacy Policy</button>
          <button @click="scrollTo('terms')" class="hover:text-gray-400">Terms & Conditions</button>
          <button class="bg-primary hover:bg-blue-800 text-white px-4 py-2 rounded">
            <a href="https://app.futuremanagment.com/">Login/Signup</a>
          </button>
        </div>
      </div>
    </header>
    
    <div class="content pt-40">
      <section id="disclaimer" class="scroll-mt-30">
        <h2>Disclaimer</h2>
        <p><strong>Last Updated:</strong> [Insert Date]</p>
        <p>Welcome to the website of <strong>Future Management Services</strong>. By using our website and services, you agree to the following terms and conditions. If you do not agree to these terms, please do not use our website or services. This disclaimer is subject to change without prior notice.</p>
        
        <h3>1. General Information</h3>
        <p>The information provided by <strong>Future Management Services</strong> on this website is for general informational purposes only. All information on the website is provided in good faith; however, we make no representation or warranty of any kind, express or implied, regarding the accuracy, adequacy, validity, reliability, or completeness of any information on the website.</p>
        <p><strong>Future Management Services</strong> is based in India and operates in accordance with Indian laws. By accessing our website, you agree to be bound by the laws applicable in India.</p>
        
        <h3>2. No Investment Advice</h3>
        <p>The content on this website, including but not limited to our algorithmic trading app, trading strategies, financial tools, and educational materials, is provided for informational purposes only and does not constitute financial, investment, tax, or legal advice. You should consult with a qualified financial advisor before making any investment decisions. <strong>Future Management Services</strong> shall not be responsible for any investment decisions made based on the information provided on this website.</p>
        
        <h3>3. Risk Disclaimer</h3>
        <p>Trading in equities, commodities, futures, and options carries a high level of risk and may not be suitable for all investors. You should carefully consider your financial situation, objectives, and risk tolerance before engaging in any form of trading. Past performance is not indicative of future results, and there is a possibility of substantial losses in trading. <strong>Future Management Services</strong> does not guarantee any specific outcome or profit and shall not be held liable for any financial loss, direct or indirect, resulting from your use of our services.</p>
        
        <h3>4. Automated Trading Services</h3>
        <p>Our platform provides automated trading services based on pre-built strategies. While these strategies are carefully designed, they are not foolproof and may not perform as expected in all market conditions. By using our automated trading services, you acknowledge that you understand the risks involved and that <strong>Future Management Services</strong> cannot be held responsible for any losses or damages arising from the use of these services.</p>
        <p>You are solely responsible for the configuration and implementation of any trades executed via our platform, and <strong>Future Management Services</strong> shall not be liable for any errors, omissions, or delays in trading. We recommend that you regularly monitor your trading account and understand the potential risks of using automated trading systems.</p>
        
        <h3>5. Third-Party Brokers</h3>
        <p>Our platform connects to multiple third-party brokers for trading purposes. <strong>Future Management Services</strong> does not own or control these brokers and is not responsible for their services, reliability, or performance. By connecting your broker account to our platform, you acknowledge that <strong>Future Management Services</strong> is not liable for any actions, omissions, or errors on the part of third-party brokers. You agree to follow the terms and conditions of your chosen broker, and you are responsible for any fees, charges, or penalties incurred.</p>
        
        <h3>6. Limitation of Liability</h3>
        <p>To the maximum extent permitted by applicable law, <strong>Future Management Services</strong> and its affiliates, directors, officers, employees, and agents shall not be liable for any direct, indirect, incidental, special, consequential, or punitive damages arising from or in connection with your use of our website or services, even if advised of the possibility of such damages. This includes but is not limited to, damages for loss of profits, revenue, data, or other intangible losses.</p>
        
        <h3>7. No Warranty</h3>
        <p>The website and services are provided "as is" and "as available" without any warranty or condition, express, implied, or statutory. <strong>Future Management Services</strong> does not warrant that the website or its content will be uninterrupted, error-free, secure, or free from viruses or other harmful components.</p>
        
        <h3>8. Indemnification</h3>
        <p>You agree to indemnify, defend, and hold harmless <strong>Future Management Services</strong>, its affiliates, officers, directors, employees, and agents from any claims, damages, liabilities, losses, costs, or expenses (including attorneys' fees) arising from or related to your use of the website or services, your breach of these terms, or your violation of any rights of a third party.</p>
        
        <h3>9. External Links Disclaimer</h3>
        <p>Our website may contain links to third-party websites or services that are not owned or controlled by <strong>Future Management Services</strong>. We do not have any control over, and assume no responsibility for, the content, privacy policies, or practices of any third-party websites or services. You acknowledge and agree that <strong>Future Management Services</strong> shall not be responsible or liable for any damage or loss caused by or in connection with the use of any such content, goods, or services available on or through any third-party websites or services.</p>
        
        <h3>10. Changes to This Disclaimer</h3>
        <p><strong>Future Management Services</strong> reserves the right to modify or replace this Disclaimer at any time. Any changes will be effective immediately upon posting on this website. Your continued use of the website following any changes constitutes acceptance of those changes.</p>
        
        <h3>11. Contact Us</h3>
        <p>If you have any questions or concerns regarding this Disclaimer, please contact us at:</p>
        <p><strong>Future Management Services</strong></p>
        <p>Email: info@futuremanagement.com</p>
        <p>Phone: [Your Contact Number]</p>
        <p>Address: [Your Company Address, India]</p>
      </section>
      
      <section id="privacy" class="scroll-mt-30">
        <h2>Privacy Policy</h2>
        <p><strong>Last Updated:</strong> [Insert Date]</p>
        <p><strong>Future Management Services</strong> ("we," "us," "our") is committed to protecting the privacy and security of our users' personal information. This Privacy Policy outlines how we collect, use, disclose, and protect your information when you use our website and algorithmic trading platform. By using our website and services, you consent to the practices described in this policy.</p>
        
        <h3>1. Information We Collect</h3>
        <p>We collect personal and non-personal information from users to provide and improve our services. This includes:</p>
        
        <h4>a) Personal Information</h4>
        <p>When you register on our platform, connect your broker, or use our services, we may collect the following information:</p>
        <ul>
          <li>Name</li>
          <li>Email address</li>
          <li>Phone number</li>
          <li>Broker account details</li>
          <li>Financial information (e.g., trading history, transaction data)</li>
          <li>Other relevant contact information</li>
        </ul>
        
        <h4>b) Non-Personal Information</h4>
        <p>We may collect non-identifiable information through cookies, web beacons, and other technologies. This includes:</p>
        <ul>
          <li>IP address</li>
          <li>Browser type</li>
          <li>Device information</li>
          <li>Usage data (e.g., pages visited, time spent on the site)</li>
        </ul>
        
        <h3>2. How We Use Your Information</h3>
        <p>We use your personal information for the following purposes:</p>
        <ul>
          <li>To provide and maintain our services, including algorithmic trading and broker connectivity.</li>
          <li>To process your trades, manage your account, and improve the performance of our platform.</li>
          <li>To communicate with you, respond to your queries, and provide customer support.</li>
          <li>To send you updates, newsletters, and other promotional content, with your consent.</li>
          <li>To comply with legal obligations and protect our rights and interests.</li>
        </ul>
        
        <h3>3. Sharing of Information</h3>
        <p>We may share your information in the following situations:</p>
        
        <h4>a) With Third-Party Brokers</h4>
        <p>When you connect your broker account to our platform, we will share the necessary data with the respective broker to facilitate trades. We are not responsible for the privacy practices of these brokers, and you should review their privacy policies.</p>
        
        <h4>b) Service Providers</h4>
        <p>We may engage trusted third-party service providers to assist with the operation of our platform. These service providers may have access to personal information but are contractually obligated to use it only to perform services on our behalf and protect your privacy.</p>
        
        <h4>c) Legal Requirements</h4>
        <p>We may disclose your information if required by law, such as to comply with a legal obligation, respond to a court order, or to protect the safety and rights of our company, users, or others.</p>
        
        <h3>4. Data Security</h3>
        <p>We take the security of your personal information seriously and implement reasonable security measures to protect your data from unauthorized access, alteration, disclosure, or destruction. These measures include encryption, access control, and secure data storage. However, no security system is 100% secure, and we cannot guarantee the absolute security of your data.</p>
        
        <h3>5. Data Retention</h3>
        <p>We will retain your personal information for as long as necessary to fulfill the purposes outlined in this Privacy Policy or as required by law. When the retention period has expired, we will delete or anonymize your data securely.</p>
        
        <h3>6. Cookies and Tracking Technologies</h3>
        <p>Our website uses cookies and similar tracking technologies to enhance user experience and collect usage data. Cookies are small files stored on your device that help us understand how you interact with our website. You can manage your cookie preferences through your browser settings.</p>
        <p>We use cookies for the following purposes:</p>
        <ul>
          <li><strong>Essential Cookies:</strong> Required for the website to function properly.</li>
          <li><strong>Analytics Cookies:</strong> To collect data on user behavior for improving our services.</li>
          <li><strong>Advertising Cookies:</strong> To deliver relevant ads to users.</li>
        </ul>
        
        <h3>7. Your Data Rights</h3>
        <p>As a user, you have the following rights concerning your personal data:</p>
        <ul>
          <li><strong>Access:</strong> You can request a copy of the personal information we hold about you.</li>
          <li><strong>Correction:</strong> You can request corrections to your personal information if it is inaccurate or incomplete.</li>
          <li><strong>Deletion:</strong> You can request that we delete your personal information, subject to certain legal exceptions.</li>
          <li><strong>Data Portability:</strong> You have the right to receive your personal information in a structured, commonly used, and machine-readable format.</li>
        </ul>
        <p>To exercise any of these rights, please contact us at the email address provided below.</p>
        
        <h3>8. International Transfers</h3>
        <p>Your personal information may be transferred to and processed in countries other than your own, including countries outside of India. If we transfer your data to another country, we will ensure appropriate safeguards are in place to protect your information in accordance with applicable privacy laws.</p>
        
        <h3>9. Children's Privacy</h3>
        <p>Our website and services are not intended for individuals under the age of 18. We do not knowingly collect personal information from  children under 18. If we become aware that we have inadvertently collected such information, we will take steps to delete it.</p>
        
        <h3>10. Changes to this Privacy Policy</h3>
        <p>We may update this Privacy Policy from time to time to reflect changes in our practices, legal requirements, or for other reasons. Any changes will be effective immediately upon posting the updated policy on our website. We encourage you to review this Privacy Policy periodically to stay informed about how we are protecting your information.</p>
        
        <h3>11. Contact Us</h3>
        <p>If you have any questions, concerns, or requests regarding this Privacy Policy, please contact us at:</p>
        <p><strong>Future Management Services</strong></p>
        <p>Email: privacy@futuremanagement.com</p>
        <p>Phone: [Your Contact Number]</p>
        <p>Address: [Your Company Address, India]</p>
      </section>
      
      <section id="terms" class="scroll-mt-30">
        <h2>Terms and Conditions</h2>
        <p><strong>Last Updated:</strong> [Insert Date]</p>
        <p>Welcome to the website of <strong>Future Management Services</strong> ("we," "us," "our"). By accessing and using our website and services, you ("User," "you," "your") agree to be bound by these Terms and Conditions. If you do not agree to these terms, please do not use our website or services. These Terms and Conditions are subject to change without prior notice.</p>
        
        <h3>1. Acceptance of Terms</h3>
        <p>By registering, accessing, or using our platform, you agree to comply with and be bound by these Terms and Conditions, along with our Privacy Policy and any other guidelines or policies referenced herein. You confirm that you are at least 18 years of age and legally eligible to enter into this agreement.</p>
        
        <h3>2. Services Provided</h3>
        <p><strong>Future Management Services</strong> offers an algorithmic trading web application that allows users to connect to various brokers, implement automated trading strategies, and trade in equity, commodities, futures, and options markets. Our platform includes pre-built trading strategies designed to suit different financial goals and risk appetites.</p>
        
        <h3>3. Disclaimer of Investment Advice</h3>
        <p>The content on our website and the services provided by <strong>Future Management Services</strong> do not constitute financial, investment, or legal advice. We do not provide personalized investment recommendations or advice. Users should consult with a qualified financial advisor before making any investment decisions. We make no guarantees regarding the performance of any trading strategy and shall not be held liable for any losses incurred.</p>
        
        <h3>4. Risk Acknowledgement</h3>
        <p>Trading in financial markets carries a high level of risk. By using our services, you acknowledge that:</p>
        <ul>
          <li>You are aware of the risks associated with trading in equities, commodities, futures, and options.</li>
          <li>You understand that past performance does not guarantee future results.</li>
          <li>You assume full responsibility for any losses, damages, or liabilities resulting from your trading activities.</li>
          <li>You are solely responsible for any trades made using our platform and understand that <strong>Future Management Services</strong> is not liable for any financial loss or damage you may incur.</li>
        </ul>
        
        <h3>5. User Obligations</h3>
        <p>By using our services, you agree to the following:</p>
        <ul>
          <li>You will provide accurate, current, and complete information during the registration process.</li>
          <li>You will maintain the confidentiality of your account credentials and be responsible for all activities conducted under your account.</li>
          <li>You will use our platform and services only for lawful purposes and in compliance with all applicable laws and regulations.</li>
          <li>You will not engage in any activity that could harm, disrupt, or interfere with the operation of our website or services.</li>
        </ul>
        
        <h3>6. Account Registration and Security</h3>
        <p>To use our services, you must create an account and provide certain information. You are responsible for maintaining the confidentiality of your account information, including your password, and for all activities that occur under your account. You agree to notify us immediately of any unauthorized use or breach of security.</p>
        <p>We reserve the right to suspend or terminate your account if we suspect any unauthorized activity or breach of these Terms and Conditions.</p>
        
        <h3>7. Use of Automated Trading Services</h3>
        <p>Our platform allows users to engage in automated trading by connecting their broker accounts. By using this feature, you acknowledge and agree that:</p>
        <ul>
          <li>You have a clear understanding of the risks associated with automated trading.</li>
          <li>You are responsible for configuring and managing your trading strategies.</li>
          <li><strong>Future Management Services</strong> is not liable for any errors, omissions, or delays in trades executed via automated trading systems.</li>
        </ul>
        
        <h3>8. Fees and Charges</h3>
        <p>Access to certain features of our platform may require the payment of fees. Any applicable fees will be displayed on our website, and you agree to pay all fees associated with your use of our services. All payments are non-refundable unless otherwise specified.</p>
        
        <h3>9. Intellectual Property</h3>
        <p>All content, logos, designs, trademarks, and other intellectual property displayed on our website are the property of <strong>Future Management Services</strong> or our licensors. You may not reproduce, distribute, modify, or create derivative works from our intellectual property without our prior written consent.</p>
        
        <h3>10. Limitation of Liability</h3>
        <p>To the maximum extent permitted by law, <strong>Future Management Services</strong> and its affiliates, directors, officers, employees, and agents shall not be liable for any direct, indirect, incidental, special, consequential, or punitive damages arising out of or related to your use of our services, even if advised of the possibility of such damages. This includes but is not limited to damages for loss of profits, revenue, data, or other intangible losses.</p>
        
        <h3>11. Indemnification</h3>
        <p>You agree to indemnify, defend, and hold harmless <strong>Future Management Services</strong>, its affiliates, officers, directors, employees, and agents from any claims, damages, liabilities, losses, costs, or expenses (including attorneys' fees) arising out of or related to your use of the website or services, your breach of these Terms and Conditions, or your violation of any rights of a third party.</p>
        
        <h3>12. Termination of Services</h3>
        <p>We reserve the right to suspend, limit, or terminate your access to our services at any time, without prior notice, for any reason, including but not limited to your breach of these Terms and Conditions. Upon termination, all rights granted to you under these terms will cease immediately, and you must discontinue all use of the services.</p>
        
        <h3>13. Governing Law</h3>
        <p>These Terms and Conditions are governed by and construed in accordance with the laws of India. Any disputes arising out of or related to these terms shall be subject to the exclusive jurisdiction of the courts located in [Your City, India].</p>
        
        <h3>14. Modifications to Terms and Services</h3>
        <p>We may modify these Terms and Conditions from time to time. Any changes will be effective immediately upon posting the updated terms on our website. Your continued use of our website and services constitutes your acceptance of the modified terms.</p>
        
        <h3>15. Contact Us</h3>
        <p>If you have any questions, concerns, or requests regarding these Terms and Conditions, please contact us at:</p>
        <p><strong>Future Management Services</strong></p>
        <p>Email: support@futuremanagement.com</p>
        <p>Phone: [Your Contact Number]</p>
        <p>Address: [Your Company Address, India]</p>
      </section>
    </div>
  </div>
</template>

<script>
import { ref, onMounted, watch } from 'vue';
import { useRoute } from 'vue-router';

export default {
  name: 'TermsAndConditions',
  setup() {
    const sidebarOpen = ref(false);
    const route = useRoute();

    const toggleSidebar = () => {
      sidebarOpen.value = !sidebarOpen.value;
    };

    const scrollTo = (sectionId) => {
      const element = document.getElementById(sectionId);
      if (element) {
        const yOffset = -150; // Adjust this value to fine-tune the scroll position
        const y = element.getBoundingClientRect().top + window.pageYOffset + yOffset;
        window.scrollTo({top: y, behavior: 'smooth'});
      }
      if (sidebarOpen.value) {
        toggleSidebar();
      }
    };

    const handleHash = () => {
      const hash = window.location.hash.substring(1);
      if (hash) {
        scrollTo(hash);
      }
    };

    onMounted(() => {
      handleHash();
    });

    watch(() => route.hash, handleHash);

    return {
      sidebarOpen,
      toggleSidebar,
      scrollTo
    };
  }
}
</script>

<style scoped>
.terms-container {
  font-family: Arial, sans-serif;
  color: #333333;
  background-color: #ffffff;
  min-height: 100vh;
}

.content {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
}

section {
  margin-bottom: 40px;
}

h2 {
  color: #31427a;
  font-size: 24px;
  margin-bottom: 15px;
  padding-top: 20px; /* Added padding to ensure visibility */
}

h3 {
  color: #31427a;
  font-size: 20px;
  margin-top: 20px;
  margin-bottom: 10px;
}

h4 {
  color: #31427a;
  font-size: 18px;
  margin-top: 15px;
  margin-bottom: 10px;
}

p {
  line-height: 1.6;
  margin-bottom: 15px;
}

ul {
  margin-bottom: 15px;
  padding-left: 20px;
}

li {
  margin-bottom: 5px;
}

img {
  max-width: none;
  object-fit: contain;
}

@media (max-width: 768px) {
  .content {
    padding: 20px 15px;
  }
}
</style>