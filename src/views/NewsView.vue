<template>
    <div class="container" v-if="data.id === 'News'">
        <div class="container__news">
            <div class="container__news_title">
                <h2>{{ data.title }}</h2>
                <span> {{ data.date }}</span>
            </div>
            <div class="container__news_content">
                <img :src="data.img" alt="">
                <p>
                    {{ data.description }}
                    <router-link to="/placeholder">More details...</router-link>
                </p>
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
        width: 70vw;
      
        &__news {
            width: 100%;
            display: flex;
            flex-direction: column;
            margin-bottom: 50px;
      
            &_title {
                display: flex;
                align-items: center;
                justify-content: space-between;
                border-radius: 8px;
                background-color: black;
                color: white;
                margin-bottom: 5px;

                h2 {
                    font-size: 16px;
                }

                h2, span {
                    margin: 5px;
                }
            }

            &_content {
                display: flex;
                align-items: stretch;
                justify-content: space-between;
                gap: 5px;

                img{
                    width: 50%;
                    height: 100%;
                }

                p {
                    display: flex;
                    align-items: flex-end;
                    justify-content: space-between;
                    flex-direction: column;
                    border-radius: 8px;
                    background-color: rgba(128, 128, 128, 0.219);
                    margin: 0;
                    padding: 15px 30px;
                    text-align: left;
                    
                    a {
                        font-weight: bold;
                        color: blue;
                        border-radius: 8px;
                        padding: 5px;

                        &:hover {
                            background: rgb(0, 0, 0);
                            transition: 0.5s;
                            border-radius: 8px;
                            padding: 5px;
                            color: white;
                        }
                    }
                }

                @media screen and (max-width: 1200px) {
                    flex-direction: column;
                    img {
                        width: 100%;
                        height: 100%;
                    }

                }
            }
        }

        @media screen and (max-width: 768px) {
            width: 95vw;
        }
    }
</style>
