<template>
    <div class="container" v-if="data.id === 'Main'">
      <img class="container__img" :src="data.image" alt="">
      <div class="container__text">
        <h2> {{ data.title }} </h2>
        <p> {{ data.description }} </p>
        <router-link class="container__link" :to="{ name: data.link }">{{ data.label }}</router-link>
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
      max-width: 70%;
      margin: 0 auto 50px;
      overflow: hidden; 
      justify-content: space-between;
      border-bottom: 1px solid rgba(0, 0, 0, 0.3);
      padding-bottom: 20px;
      display: flex;
      gap: 3%;

        &:nth-child(even) {
          flex-direction: row-reverse;
        }

        &:last-child {
          border: none;
        }

        &__img {
          width: 50%;
        }

        &__text {
          display: flex;
          flex-direction: column;
        }

        &__link {
          font-weight: bold;
          color: #2c3e50;
          border-radius: 8px;
          background-color: rgba(127, 255, 212, 0.534);
          padding: 5px;
          white-space: nowrap;

          &:hover {
            background-color: greenyellow;
            transition: 0.5s;
          }
        }

      @media screen and (max-width: 1300px) {
          max-width: 95%;
      }

      @media screen and (max-width: 850px) {
        flex-direction: column;
        &:nth-child(even) {
          flex-direction: column;
        }
      }
    }
</style>