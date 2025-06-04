<template>
    <div class="slider-container">
        <h2>My Projects</h2>
        <Swiper :modules="[Navigation, Pagination]" :slides-per-view="3" :space-between="30" navigation pagination
            class="custom-swiper">
            <SwiperSlide v-for="(item, index) in projects" :key="index" class="card">
                <img :src="getImage(item.image)" alt="project image" class="swiper-img" />
                <h3>{{ item.text }}</h3>
                <p>{{ item.about }}</p>
                <a v-if="item.link" :href="item.link" target="_blank" rel="noopener noreferrer" class="card-button">
                    {{ item.button }}
                </a>
            </SwiperSlide>
        </Swiper>
    </div>
</template>

<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import { Navigation, Pagination } from 'swiper/modules';
import { ref } from 'vue';

const getImage = (name) => new URL(`../assets/photos/${name}`, import.meta.url).href;

const projects = ref([
    {
        image: 'estatein.png',
        text: 'Estatein',
        about: "I won't say much, just go and judge for yourself.",
        button: 'GitHub',
        link: 'https://github.com/Tolordava5/Estetaein',
    },
    {
        image: 'Crypto.png',
        text: 'Cryto',
        about: "I won't say much, just go and judge for yourself.",
        button: 'GitHub',
        link: 'https://github.com/Tolordava5/Estetaein',
    },
    {
        image: 'login.png',
        text: 'Log In',
        about: "I won't say much, just go and judge for yourself.",
        button: 'GitHub',
        link: 'https://github.com/Tolordava5/Login_Form',
    },
    {
        image: 'user_posts.png',
        text: 'User-Posts',
        about: "I won't say much, just go and judge for yourself.",
        button: 'GitHub',
        link: 'https://github.com/Tolordava5/User_Posts',
    },
    {
        image: 'cosmo.png',
        text: 'Register',
        about: "I won't say much, just go and judge for yourself.",
        button: 'GitHub',
        link: 'https://github.com/Tolordava5/User_Posts',
    },
    {
        image: 'products.png',
        text: 'Products',
        about: "I won't say much, just go and judge for yourself.",
        button: 'GitHub',
        link: 'https://github.com/Tolordava5/Product_Cards',
    },
]);
</script>

<style scoped>
h2 {
    display: flex;
    color: white;
    justify-content: center;
    font-size: 46px;
}

.slider-container {
    display: flex;
    flex-direction: column;
    gap: 50px;
    padding: 40px;
    padding-top: 150px;
    background: linear-gradient(to left, #161616, #1a1128);
    min-height: 100vh;
    overflow-x: hidden;
}

.custom-swiper {
    width: 100%;
    overflow: visible;
    margin-left: 10px;
}

.card {
    position: relative;
    overflow: hidden;
    border-radius: 16px;
    background-color: rgba(255, 255, 255, 0.082);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    padding: 16px;
    cursor: pointer;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.card img {
    width: 100%;
    max-width: 100%;
    transition: transform 0.4s ease;
    border-radius: 8px;
    display: block;
    margin: 0 auto;
}

.card:hover img {
    transform: scale(1.1);
}

.card h3 {
    padding-top: 20px;
    color: white;
    font-size: 24px;
}

.card p {
    color: white;
    padding-top: 12px;
    font-size: 18px;
}

.card a {
    margin-top: 20px;
    text-align: center;
}

.card-button {
    display: inline-block;
    padding: 10px 24px;
    background-color: transparent;
    color: white;
    border: 2px solid #8b5cf6;
    border-radius: 8px;
    text-decoration: none;
    width: 150px;
    transition: all 0.3s ease;
}

.card-button:hover {
    background-color: #8b5cf6;
    color: white;
    transform: scale(1.05);
}

::v-deep .swiper-button-next,
::v-deep .swiper-button-prev {
    color: #fff;
    padding: 12px;
    transition: all 0.3s;
}

::v-deep .swiper-button-prev {
    left: -30px;
}

::v-deep .swiper-button-next {
    right: -30px;
}

::v-deep .swiper-pagination-bullet {
    background: #ccc;
    opacity: 1;
}

::v-deep .swiper-pagination-bullet-active {
    background: #8b5cf6;
}
::v-deep .swiper-pagination {
  bottom: -20px; 
  position: relative; 
  margin-top: 20px;   
}
</style>
