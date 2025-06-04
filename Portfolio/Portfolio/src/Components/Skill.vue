<template>
    <div class="skill">
        <H2>My skills</H2>

        <div class="skill-cards">
            <div v-for="(item, index) in cards" :key="index" class="cards" :style="{
                borderColor: item.borderColor,
                boxShadow: `0 4px 12px ${item.shadowColor}`
            }">
                <img :src="getImage(item.image)" alt="cards image" class="cards-img">
                <p>{{ item.text }}</p>
            </div>
        </div>
    </div>
</template>
<style scoped>
h2 {
    font-size: 46px;
    margin: 0 auto;
    margin-bottom: 50px;
    display: flex;
    justify-content: center;
    padding-top: 150px;
}

.skill {
    background: linear-gradient(to left, #161616, #1a1128);
    color: white;
}

.skill-cards {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 50px;
    padding: 20px;
    width: 1000px;
    margin: 0 auto;
}


.cards {
    width: 200px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    border: 2px solid;
    padding: 16px;
    border-radius: 12px;
    background-color: #1e1e1e;
    transition: transform 0.2s ease;
    cursor: pointer;
}

.cards:hover {
    transform: scale(1.05);
}

.cards-img {
    width: 80px;
    height: 80px;
    object-fit: contain;
    margin-bottom: 10px;
}
</style>


<script setup>
import { ref } from 'vue'

const getImage = (name) => new URL(`../assets/photos/${name}`, import.meta.url).href


const cards = ref([
    {
        image: 'HTML.png',
        text: 'HTML',
        shadowColor: '#e44d2666',
        borderColor: '#E44D26'

    },
    {
        image: 'CSS.png',
        text: 'CSS',
        borderColor: '#1572B6',
        shadowColor: '#1572b666'
    },
    {
        image: 'JavaScript.png',
        text: 'JavaScript',
        borderColor: '#F7DF1E', 
        shadowColor: '#f7df1e66'
    },
    {
        image: 'Python.png',
        text: 'Python',
        borderColor: '#306998', 
        shadowColor: '#30699866'
    },
    {
        image: 'React.png',
        text: 'React',
        borderColor: '#61DAFB',
         shadowColor: '#61dafb66'
    }, {
        image: 'Typescript.png',
        text: 'TypeScript',
        borderColor: '#3178C6',
        shadowColor: '#3178c666'
    },
    {
        image: 'Tailwind.png',
        text: 'Tailwind',
        borderColor: '#38B2AC',
        shadowColor: '#38b2ac66'
    },
    {
        image: 'Vue.png',
        text: 'Vue.js',
        borderColor: '#42b883',
        shadowColor: '#42b88366'
    },
    {
        image: 'Figma.png',
        text: 'Figma',
        borderColor: '#F24E1E',
        shadowColor: '#f24e1e66'
    },

])

</script>