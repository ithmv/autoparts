<template>
    <main class="main">
        <router-view   v-for="item in data" :key="item.id" :data="item" />
    </main>
</template>

<script lang="ts">
  import { defineComponent } from 'vue';
  import data from '../data.json';


  export default defineComponent({


  data() {
    return {
      data: data,
    };
  },

  });
</script>

<style scoped lang="scss">
</style>