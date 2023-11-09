<template>
    <div class="container" v-if="data.id === 'Contacts'">
      <div class="container__contacts"> 
        <a class="container__contacts_adress" :href="data.adress_link" target="_blank">
          <h2>We are located at:</h2>
          <h3>{{ data.adress }}</h3>
          <p>{{ data.adress_time }}</p>
          <span>{{ data.adress_description }}</span>
        </a>
        <a class="container__contacts_phone" :href="'tel:' + data.phone">
            <h2>Our phone:</h2>
            <p>&#128222; {{ data.phone }}</p>
            <span>{{ data.phone_time }}</span>
        </a>
      </div>
      <iframe :src="data.map" width="600" height="450" style="border:0;" allowfullscreen="false" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
      <div class="container__social">
        <h2>Our social networks:</h2>
        <div class="container__social_links">
        <a v-for="(link, index) in data.link" :key="index" :href="link" target="_blank">
          <img :src="data.icons[index]" alt="">
          {{ data.social[index] }}
        </a>
        </div>
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
    });
  </script>
  
  <style lang="scss" scoped>
  .container {
    display: flex;
    flex-direction: column;
    width: 80vw;
    justify-content: space-around;
    align-items: flex-start;
    gap: 20px;

    iframe {
      border-radius: 8px;
      width: 100%;
      box-shadow: 0 0 10px 0 black;
      height: 50vh;
    }

    &__social {
      display: flex;
      flex-direction: column;
      width: 100%;
      align-items: center;

      &_links {
        width: 80%;
        display: flex;
        justify-content: center;
        gap: 50px;
        border-radius: 8px;
        box-shadow: 0 0 10px 0 black;
        
        a {
          display: flex;
          align-items: center;
          gap: 4px;
          padding: 10px;

          img {
            width: 25px;
            height: 25px;
          }
          &:hover {
            background-color: lightcyan;
            transition: .3s;
            box-shadow: 0 0 5px 0 black;
          }
        }
      }
    }

    &__contacts {
      width: 100%;
      display: flex;
      align-items: flex-end;
      justify-content: center;
      gap: 20px;
      text-align: left;

      &_adress {
        width: 60%;

        h2 {
          margin-top: 0;
        }
      }

      &_phone {
        p, h2 {
          font-weight: bold;
          margin: 5px;
        }
      }

      &_adress, &_phone {
        border-radius: 8px;
        padding: 20px;
        box-shadow: 0 0 10px 0 black; 

        &:hover {
          background-color: rgba(173, 216, 230, 0.519);
          transition: .7s;
        }
      }
    }

    @media screen and (max-width: 920px) {

      &__social {
        &_links {
          flex-direction: column;
          align-items: center;
          gap: 0;
        }
      }

      &__contacts {
        flex-direction: column;
        align-items: center;
        gap: 20px;

        &_adress {
        width: 90%;
        }

        &_phone {
          display: none;
        }
      }


    }
  }
  </style>