<template>
  <div class="container" v-if="data.id === 'Catalog'">
    <form @submit.prevent="submitOrder">
      <div class="container__form">
        <label for="firstName">Name:</label>
        <input type="text" id="firstName" v-model="firstName" required>
      </div>

      <div class="container__form">
        <label for="lastName">Last name:</label>
        <input type="text" id="lastName" v-model="lastName" required>
      </div>

      <div class="container__form">
        <label for="address">Address:</label>
        <input type="text" id="address" v-model="address" required>
      </div>

      <div class="container__form">
        <label for="phoneNumber">Phone number:</label>
        <input type="tel" id="phoneNumber" v-model="phoneNumber" required>
      </div>

      <div class="container__form">
        <label for="email">Email:</label>
        <input type="email" id="email" v-model="email" required>
      </div>

      <div class="container__form" id="acceptPolicy">
        <router-link to="/policy" target="_blank">I accept Privacy policy</router-link>
        <input type="checkbox" id="acceptPolicy" v-model="acceptPolicy" required>
      </div>

      <button type="submit" :disabled="!acceptPolicy">Order</button>
    </form>
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
        firstName: '',
        lastName: '',
        address: '',
        phoneNumber: '',
        email: '',
        acceptPolicy: false,
      };
    },
    methods: {
      submitOrder() {
      },
    },
  });
  </script>
  
  <style lang="scss" scoped>
  .container {
    width: 100%;
    margin: 0 auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);

    &__form {
      margin-bottom: 15px;
    
      label {
        display: block;
        font-weight: bold;
      }
    
      input[type="text"],
      input[type="tel"],
      input[type="email"] {
        width: 100%;
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
        font-size: 16px;
      }
    
      button {
        background-color: #007bff;
        color: #fff;
        border: none;
        border-radius: 5px;
        padding: 10px 20px;
        font-size: 16px;
        cursor: pointer;
    
        &:hover {
          background-color: #0056b3;
        }
    
        &:disabled {
          background-color: #ccc;
          cursor: not-allowed;
        }
      }
    }
  }

  #acceptPolicy {
    display: flex;
    align-items: center;
    gap: 50px;

    a {
        color: #007bff;
        font-weight: bold;
    }
  }
  </style>
  
  