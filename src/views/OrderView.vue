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

      <button id="submit" type="submit" :disabled="!acceptPolicy">Order</button>
    </form>

    <div v-if="thankYouMessage" class="thank-you-message">
      Thank you for your order!
    </div>
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
      thankYouMessage: false,
    };
  },
  methods: {
    submitOrder() {

      this.thankYouMessage = true;
      setTimeout(() => {
        this.thankYouMessage = false;
        setTimeout(() => {
          location.reload();
        }, 100);
      }, 3000);
    },
  },
});
</script>

<style lang="scss" scoped>
.container {
  width: 100vw;
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
}
  #submit {
    width: 100%;
    border-radius: 8px;
    padding: 10px;
    border: none;
    background-color: blue;
    color: white;
    cursor: pointer;
    
    &:hover {
      box-shadow: 0 0 10px 0 black;
      transition: 0.5s;
      background-color: rgba(0, 0, 255, 0.486);
    }
    
    &:disabled {
        background-color: #ccc;
        cursor: not-allowed;
        box-shadow: none;
        color : black;
      }
  }

.thank-you-message {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  background-color: #007bff;
  color: #fff;
  text-align: center;
  padding: 100px 10px;
  font-size: 18px;
  animation: slide-down 0.5s ease-in-out, fade-out 3s 0.5s;
}

@keyframes slide-down {
  0% {
    transform: translateY(-100%);
  }
  100% {
    transform: translateY(0);
  }
}

@keyframes fade-out {
  0% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}
</style>
