<template>
  <div class="cookie-notification" v-if="!cookiesAccepted">
    <p>Мы используем куки для улучшения вашего опыта. Продолжая использовать сайт, вы соглашаетесь с нашей политикой использования куки.</p>
    <button @click="acceptCookies">Принять</button>
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
