<template>
  <div class="container" v-if="data && data.id === 'Catalog'">
    <div class="container__title">
      <h1>{{ data.title }}</h1>
      <span>{{ data.subtitle }}</span>
    </div>
    <div class="container__parts">
      <h2>Select car brand</h2>
      <div class="container__parts_item" v-for="(item, index) in data.brands" :key="index">
        <section @click="toggleCategoriesVisibility(index)" :class="{ 'active': categoriesVisible[index] }">
          <img :src="data.logo[index]" alt="Brand Logo">
          <span>{{ item }}</span>
        </section>
        <div class="container__parts_categories" :class="{ 'slide-in': categoriesVisible[index], 'slide-out': !categoriesVisible[index] }">
          <router-link v-for="(category, categoryIndex) in data.parts" :key="categoryIndex" :to="'/order'">
            <img :src="data.parts_images[categoryIndex]" alt="">
            {{ category }}
          </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
  import { defineComponent, ref, computed } from 'vue';

  export default defineComponent({
    props: {
      data: {
        type: Object,
        required: true,
      },
    },
    setup(props) {
      const categoriesVisible = ref(Array(props.data.brands?.length || 0).fill(false));

      function toggleCategoriesVisibility(index: number) {
        categoriesVisible.value[index] = !categoriesVisible.value[index];
      }

      return {
        categoriesVisible,
        toggleCategoriesVisibility
      };
    },
  });
</script>
 
<style lang="scss" scoped>
    .container {
        flex-direction: column;
        position: relative;

        &__title {
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 80%;

            h1, span {
                background-color: rgba(0, 0, 0, 0.829);
                padding: 15px;
                margin: 5px;
                border-radius: 8px;
                color: white;
                width: 100%;
            }

            @media screen and (max-width: 760px) {
              width: 100%;
            }
        }

        &__parts {
          display: flex;
          flex-direction: column;
          gap: 10px;


          &_item {
            display: flex;
            flex-direction: column;
          }

          section {
              display: flex;
              align-items: center;
              justify-content: center;
              background-color: white;
              padding: 10px;
              border-radius: 8px;
              box-shadow: 0 0 10px 0 black;
              cursor: pointer;
              transition: background-color 0.5s;

              img {
                width: 10%;
              }

              span {
                font-weight: bolder;
              }

              &:hover {
                background-color: rgba(2, 201, 236, 0.25);
              }

              &.active {
                background-color: lightblue;
              }

              @media screen and (max-width: 760px) {
                width: 90vw;
                margin: 0 auto;
                
              }
          }


          &_categories {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            margin: 0 auto;
            justify-content: center;
            max-height: 0;
            overflow: hidden;
            transition: max-height .9s ease;

            &.slide-in {
              max-height: 3000px;
            }
            &.slide-out {
              max-height: 0;
            }
            
            a {
              padding: 10px;
              border-radius: 8px;
              background-color: white;
              box-shadow: 0 0 5px 0 black;
              margin: 10px;
              display: flex;
              flex-direction: column;
              gap: 10px;

              &:hover {
                background-color: rgba(0, 0, 0, 0.829);
                color: white;
                transition: .5s;
              }

              @media screen and (max-width: 760px) {
                width: 90vw;
              }
            }

            @media screen and (max-width: 1170px) {
              grid-template-columns: repeat(2, 1fr);
            }

            @media screen and (max-width: 760px) {
              grid-template-columns: repeat(1, 1fr);
            }
          }
        }
    }
</style>