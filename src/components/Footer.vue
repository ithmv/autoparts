<template>
    <div>
      <footer class="footer">
        <div class="footer__info">
           <p>Dalas Auto Parts LLC</p>
           <p>TIN 123456789</p>
           <p>OGRN 123456789012</p>
         </div>
        <router-link to="/policy" target="_blank">Privacy Policy</router-link>
      </footer>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    
  });
  </script>
  
  <style scoped lang="scss">
  .footer {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
    max-height: 100px;
    padding: 10px;
    width: 90vw;
    background-color: lightgray;
    border-top-left-radius: 16px;
    border-top-right-radius: 16px;
    box-shadow: 0 -10px 20px 0 lightgray;
  
    a {
      font-weight: bold;
      color: #03509e;
      text-decoration: underline;
      font-size: 14px;
      border: none;
      background: none;
    }
  
    &__info {
      text-align: left;
      display: flex;
      gap: 15px;
  
      p {
        margin: 0;
        font-size: 12px;
        white-space: nowrap;
      }
    }
  
    @media screen and (max-width: 1200px) {
      flex-direction: column;
  
      p {
        text-align: center;
        font-size: 10px;
        margin-bottom: 10px;
      }
    }
  }
  </style>