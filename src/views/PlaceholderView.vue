<template>
    <div class="container" v-if="data.id === 'Placeholder'">
    <h1>{{ data.title }}</h1></div>
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
</style>