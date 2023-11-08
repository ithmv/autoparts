<template>
  <div class="container" v-if="data.id === 'About'">
    <div class="container__title">
      <h1>{{ data.title }}</h1>
      <span>{{ data.description }}</span>
    </div>

    <div class="container__prefs">
      <span
        class="container__prefs_item"
        v-for="(item, index) in data.list"
        :key="index"
        :style="{ backgroundColor: getRandomColor(index) }">
          {{ item }}
      </span>
    </div>

    <p>{{ data.content }}</p>
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
    methods: {
      getRandomColor(index: number) {
        const hue = (index * 137) % 360; 
        return `hsla(${hue}, 60%, 50%, 0.3)`; 
      },
    },
  });
</script>

<style lang="scss" scoped>
.container {
  border-radius: 8px;
  padding: 25px;
  flex-direction: column;
  margin: 0 auto;
  
  &__title {
    background-image: url(../assets/aboutus.jpg);
    background-size: cover;
    background-repeat: no-repeat;
    display: flex;
    flex-direction: column;
    gap: 10px;
    background-color: rgba(240, 248, 255, 0.5);
    border-radius: 8px;
    color: black;
    padding: 105px 0;
    margin-bottom: 40px;
    font-weight: bold;

    h1, span {
      background-color: rgba(240, 248, 255, 0.8);
      margin: 0;   
      padding: 10px;
    }
  }

  &__prefs {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    width: 80%;
    margin-bottom: 50px;

    &_item {
      display: flex;
      align-items: center;
      min-height: 100px;
      border-radius: 8px;
      padding: 10px;
      text-align: center;
      color: black;
      font-weight: bold;
    }

    @media screen and (max-width: 1200px) {
      width: 100%;
    }

    @media screen and (max-width: 900px) {
      grid-template-columns: repeat(2, 1fr);
    }

    @media screen and (max-width: 500px) {
      grid-template-columns: repeat(1, 1fr);
    }
  }

  p {
    width: 100%;
    background-color: rgb(0, 0, 0);
    padding: 20px;
    border-radius: 8px;
    color: white;
  }
}
</style>