<template>
  <div class="cookie-notification" v-if="!cookiesAccepted">
    <p>We use cookies to improve your experience. By continuing to use the site, you agree to our cookie policy.</p>
     <button @click="acceptCookies">Accept</button>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, onMounted } from 'vue';

export default defineComponent({
  setup() {
    const cookiesAccepted = ref(false);

    // Функция для установки куки и скрытия уведомления
    const acceptCookies = () => {
      const expirationDate = new Date();
      expirationDate.setDate(expirationDate.getDate() + 365); // Куки на год
      document.cookie = 'cookiesAccepted=true; expires=' + expirationDate.toUTCString();
      cookiesAccepted.value = true;
    };

    // Проверяем, приняты ли куки при загрузке страницы
    onMounted(() => {
      if (document.cookie.split(';').some((item) => item.trim().startsWith('cookiesAccepted='))) {
        cookiesAccepted.value = true;
      }
    });

    return { cookiesAccepted, acceptCookies };
  },
});
</script>

<style scoped>
.cookie-notification {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  background: #333;
  color: #fff;
  padding: 10px;
  text-align: center;
}

.cookie-notification button {
  background: #00f;
  color: #fff;
  border: none;
  padding: 5px 10px;
  cursor: pointer;
}
</style>
