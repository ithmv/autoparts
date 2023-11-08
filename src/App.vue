<template>
  <Header v-for="item in data" :key="item.id" :data="item" />
  <Main />
  <Footer />
  <CookieNotification />
</template>

<script lang="ts">
  import { defineComponent } from 'vue';
  import data from './data.json';
  import Header from './components/Header.vue';
  import Main from './components/Main.vue';
  import Footer from './components/Footer.vue';
  import CookieNotification from './components/CookieNotification.vue';

  export default defineComponent({
    name: 'App',
    components: {
      Header,
      Main,
      Footer,
      CookieNotification
    },

  data() {
    return {
      data: data,
    };
  },

  });
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  display: flex;
  gap: 40px;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  height: 100vh;
}

body {
  margin: 0 auto;
  background-color: rgba(160, 194, 245, 0.151);
}

.container {
  max-width: 80vw;
  display: flex;
  height: auto;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
}

a {
  text-decoration: none;
  color: #000;
}

img {
  border-radius: 8px;
}
</style>
