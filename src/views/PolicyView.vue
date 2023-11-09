<template>
  <div class="container" v-if="data.id === 'About'">
           <h1>Privacy Policy</h1>
             <p><strong>Last update:</strong> 11/09/2023</p>
             <p>Welcome to the CarTime website, specializing in the sale of auto parts. Your privacy is very important to us and we work hard to protect your personal information. Below is our privacy policy to help you understand how we collect, use, disclose and protect your information.</p>
             <h2>1. Information collected</h2>
             <p>We collect the following categories of information:</p>
             <ul>
                 <li><strong>Personal Information:</strong>Your name, contact information (email address, phone number), shipping address, and information you provide when placing an order.</li>
                 <li><strong>Payment Information:</strong> To process payments, we collect information about credit cards, debit cards, or other means of payment.</li>
                 <li><strong>Site Usage Information:</strong> We collect information about how you interact with our website, including data about page views, products and services.</li>
             </ul>
             <h2>2. Use of collected data</h2>
             <p>We use your personal data for the following purposes:</p>
             <ul>
                 <li><strong>Order Processing:</strong> We use your information to process and fulfill your orders, including delivery of goods and order feedback.</li>
                 <li><strong>Customer support:</strong>Your data may be used to resolve issues and provide technical support.</li>
                 <li><strong>Marketing and Communications:</strong>We may use your information to provide you with information about our products, promotions and news, but only with your permission.</li>
             </ul>
             <h2>3. Disclosure</h2>
             <p>Your personal information may be disclosed to third parties only in the following cases:</p>
             <ul>
                 <li><strong>Partners and suppliers:</strong> We may share information with our partners and suppliers as necessary to process orders and deliver goods.</li>
                 <li><strong>Legal and Enforcement:</strong>We may disclose your information if required to do so by law or court order.</li>
             </ul>
             <h2>4. Data protection</h2>
             <p>We take measures to ensure the security of your data. We use state-of-the-art encryption and other security measures to protect your information.</p>
             <h2>5. Your rights and choices</h2>
             <p>You have the right:</p>
             <ul>
                 <li>Request access to your personal information.</li>
                 <li>Request correction of inaccurate information.</li>
                 <li>Request deletion of your information.</li>
                 <li>Withdraw consent to the processing of information for marketing purposes.</li>
             </ul>
             <h2>6. Contacts</h2>
             <p>If you have questions or comments regarding our privacy policy, please contact us at:</p>
             <p>8-800-555-35-35</p>
             <h2>7. Changes to the privacy policy</h2>
             <p>We may update this privacy policy from time to time. Any changes will be posted on this page with the date of last update.</p>
             <p>Please check this policy regularly for updates and changes.</p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    data: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {
      isPolicyOpen: false,
    };
  },
  methods: {
    openPolicy() {
      this.isPolicyOpen = true;
    },
    closePolicy() {
      this.isPolicyOpen = false;
    },
  },
});
</script>


<style lang="scss" scoped>
    .container {
        display: flex;
        flex-direction: column;
        text-align: left;
    }
</style>
