<template>
  <header class="header" v-if="data.id === 'Contacts'">
    <a class="header__logo" href="/">
        <img src="../assets/logo.png">
        <div class="header__logo_text">
            <h1>Car-Time</h1>
            <span>Spare parts in stock and on order</span>
        </div>
    </a>

    <nav class="header__nav">
        <router-link to="/">Home</router-link> |
        <router-link to="/reviews">About us</router-link> |
        <router-link to="/catalog">Catalog</router-link> |
        <router-link to="/news">News</router-link> |
        <router-link to="/contacts">Contacts</router-link>
    </nav>

    <div class="header__coords">
        <a class="header__coords_phone" :href="'tel:' + data.phone">
            <p> &#128222; {{ data.phone }}</p>
            <span>{{ data.adress_time}}</span>
        </a>
        <a class="header__coords_adress" :href="data.adress_link" target="_blank">{{ data.adress }}</a>

    </div>
    
  </header>
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

<style scoped lang="scss">
    .header {
        display: flex;
        align-items: center;
        justify-content: space-evenly;
        max-height: 100px;
        padding: 10px;
        width: 90vw;
        background-color:lightgray;
        box-shadow: 0 10px 20px 0 lightgray;
        margin: 0 auto;
        border-bottom-left-radius: 16px;
        border-bottom-right-radius: 16px;

        &__logo {
            display: flex;
            align-items: center;

            img {
                width: 20vh;
            }

            &_text {
                h1 {
                    font-style: italic;
                    margin: 0;
                    font-size: 20px;
                }

                span {
                    font-weight: bold;
                    font-size: 12px;
                }
            }
        }
            
        &__nav {
            border-radius: 16px;
            padding: 10px;
            width: 30%;
            display: flex;
            justify-content: space-evenly;
            align-items: center;

            a {
                font-weight: bold;
                color: #2c3e50;
                text-decoration: none;
                padding: 5px;
                white-space: nowrap;
                
                &:hover {
                color: rgba(0, 0, 255, 0.486);
                transition: 0.5s;
                }

                &.router-link-exact-active {
                color: blue;
                text-decoration: solid underline;
                }
            }
        }

        &__coords {
            display: flex;
            flex-direction: column;
            align-items: center;

            &_phone { 
                border-radius: 8px;
                padding: 10px;

                p {
                    margin: 0px;
                    font-weight: bold;
                }
                
                span {
                    font-size: 12px;
                }

                &:hover {
                    background-color: greenyellow;
                    transition: 0.5s;
                }
            }

            &_adress {
                font-size: 12px;
                padding: 5px;
                border-radius: 8px;
                font-weight: bold;

                &:hover {
                    text-decoration: underline;
                    transition: 0.5s;
                    background-color: rgb(0, 255, 0);
                }
            }
        }

        @media screen and (max-width: 1200px) {
            max-height: 300px;
            flex-direction: column;
            
            img {
                display: none;
            }

            nav {
                font-size: 14px;
            }

            p {
                padding: 0;
            }
        }
    }
</style>
