<template>
    <div>
      <div class="policy" v-if="isPolicyOpen">
        <section>
          <h1>Политика конфиденциальности</h1>
          <button class="policy__close" @click="closePolicy">Закрыть</button>
        </section>
        <span>
            <p><strong>Последнее обновление:</strong> 09.11.2023</p>
            <p>Добро пожаловать на сайт CarTime TOMSK, специализирующейся на продаже автозапчастей. Ваша конфиденциальность очень важна для нас, и мы прилагаем все усилия, чтобы защитить ваши личные данные. Ниже приведена наша политика конфиденциальности, чтобы вы понимали, как мы собираем, используем, раскрываем и защищаем ваши данные.</p>
            <h2>1. Собираемая информация</h2>
            <p>Мы собираем следующие категории информации:</p>
            <ul>
                <li><strong>Личные данные:</strong> Ваши имя, контактная информация (адрес электронной почты, номер телефона), адрес доставки и информацию, которую вы предоставляете при оформлении заказа.</li>
                <li><strong>Информация о платежах:</strong> Для обработки платежей мы собираем информацию о кредитных карт, дебетовых картах или других средствах оплаты.</li>
                <li><strong>Информация об использовании сайта:</strong> Мы собираем информацию о том, как вы взаимодействуете с нашим сайтом, включая данные о просмотрах страниц, продуктах и услугах.</li>
            </ul>
            <h2>2. Использование собранных данных</h2>
            <p>Мы используем ваши личные данные для следующих целей:</p>
            <ul>
                <li><strong>Обработка заказов:</strong> Мы используем ваши данные для обработки и выполнения ваших заказов, включая доставку товаров и обратную связь по заказу.</li>
                <li><strong>Клиентская поддержка:</strong> Ваши данные могут использоваться для решения вопросов и предоставления технической поддержки.</li>
                <li><strong>Маркетинг и коммуникация:</strong> Мы можем использовать вашу информацию, чтобы предоставлять вам информацию о наших продуктах, акциях и новостях, но только с вашего разрешения.</li>
            </ul>
            <h2>3. Разглашение информации</h2>
            <p>Ваша личная информация может быть разглашена третьим сторонам только в следующих случаях:</p>
            <ul>
                <li><strong>Партнерам и поставщикам:</strong> Мы можем передавать информацию нашим партнерам и поставщикам, если это необходимо для обработки заказов и доставки товаров.</li>
                <li><strong>Законодательство и правоприменение:</strong> Мы можем разглашать вашу информацию, если это требуется законом или по решению суда.</li>
            </ul>
            <h2>4. Защита данных</h2>
            <p>Мы принимаем меры для обеспечения безопасности ваших данных. Мы используем современные методы шифрования и другие меры безопасности для защиты вашей информации.</p>
            <h2>5. Ваши права и выбор</h2>
            <p>Вы имеете право:</p>
            <ul>
                <li>Запросить доступ к вашей личной информации.</li>
                <li>Запросить исправление неточной информации.</li>
                <li>Запросить удаление вашей информации.</li>
                <li>Отозвать согласие на обработку информации для маркетинговых целей.</li>
            </ul>
            <h2>6. Контакты</h2>
            <p>Если у вас есть вопросы или замечания относительно нашей политики конфиденциальности, свяжитесь с нами по следующим контактам:</p>
            <p>8-800-555-35-35</p>
            <h2>7. Изменения в политике конфиденциальности</h2>
            <p>Мы можем время от времени обновлять эту политику конфиденциальности. Любые изменения будут опубликованы на этой странице с указанием даты последнего обновления.</p>
            <p>Пожалуйста, регулярно проверяйте эту политику для обновлений и изменений.</p>
        </span>
      </div>
      <footer class="footer">
        <div class="footer__info">
          <p>ООО "Томские автозапчасти"</p>
          <p>ИНН 123456789</p>
          <p>ОГРН 123456789012</p>
        </div>
        <button @click="openPolicy">Политика конфиденциальности</button>
      </footer>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
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
  
  <style scoped lang="scss">
  .policy {
    position: absolute;
    background-color: white;
    border-radius: 16px;
    box-shadow: 0 0 20px 0 black;
    left: 0;
    top: 5%;
    display: flex;
    flex-direction: column;
    padding: 0 30px;
    width: 100%;
  
    section {
      display: flex;
      gap: 5px;
      justify-content: center;
      align-items: center;

      @media screen and (max-width: 600px) {
        flex-direction: column;
        
      }
    }
  
    span {
      text-align: left;
      width: 90%;
      padding-bottom: 200px;
  
      h2 {
        font-size: 16px;
      }
  
      p, ul {
        font-size: 14px;
      }
    }
  }
  
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
  
    button {
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