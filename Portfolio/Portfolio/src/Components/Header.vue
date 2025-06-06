<template>
  <header>
    <nav>
      <div>
        <h3><a href="Header.vue"></a>Portfolio</h3>
      </div>
      <div>
        <ul class="new-list">
          <li v-for="(item, index) in newsList" :key="index">
            <a :href="item.link">{{ item.name }}</a>
          </li>
        </ul>
      </div>
    </nav>
    <div class="mobile" :class="{ active: isActive }" @click="toggleActive">
      <div>
        <h3><a href="Header.vue"></a>Portfolio</h3>
      </div>
      <img src="../assets/Photos/List.png" alt="">
      <ul class="new-list">
        <li v-for="(item, index) in newsList" :key="index">
          <a :href="item.link">{{ item.name }}</a>
        </li>
      </ul>
    </div>
    <ul class="new-list">
      <li v-for="(item, index) in newsList" :key="index">
        <a :href="item.link">{{ item.name }}</a>
      </li>

    </ul>
  </header>
</template>

<style scoped>
* {
  color: white;
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background: linear-gradient(to left, #161616, #1a1128);

}

nav {
  display: flex;
  align-items: center;
  font-size: 30px;
  padding: 40px;
  border-bottom: 1px solid white;
  justify-content: space-between;
}

h3 {
  margin-left: 50px;
  transition: 0.3s;
  cursor: pointer;
}

h3:hover {
  color: #A259FF;
  text-shadow: 0 0 10px #A259FF, 0 0 20px #A259FF;
}

.new-list {
  list-style: none;
  display: flex;
  gap: 35px;
  cursor: pointer;
}

li a {
  text-decoration: none;
  color: white;
  transition: 0.3s;
}

li a:hover {
  text-decoration: underline;
  color: #A259FF;
}

.mobile {
  display: none;
}

.mobile+.new-list {
  display: none;
}

@media screen and (max-width:600px) {
  nav {
    display: none !important;
  }

  .mobile {
    display: grid;
    grid-template-columns: 1fr 1fr;
    background-color: transparent;
    padding: 20px;
    gap: 10px;
    border-bottom: 1px solid white;
  }
  .mobile h3{
    display: flex;
    justify-content: center;
    margin-top: 10px;
    font-size: 24px;
  }

  .mobile ul {
    display: flex;
    flex-direction: column;
    gap: 20px;
    overflow: hidden;
    max-height: 0;
    opacity: 1;
    transform: translateY(-10px);
    transition: max-height 0.6s ease, opacity 0.6s ease, transform 0.6s ease;
  }

  .mobile.active ul {
    max-height: 500px;
    opacity: 1;
    transform: translateY(0);
    display: flex;
  }
  .mobile.active a{
    font-size: 20px;
  }

  .mobile>img {
    width: 40px;
    height: 40px;
    margin-left: 100px;
    cursor: pointer;
  }

  .mobile.active>img {
    transform: rotate(360deg);
    transition: transform 0.3s ease;
  }
}
</style>

<script setup>
import { ref } from 'vue'

const newsList = ref([
  { name: "Home", link: "Home.vue" },
  { name: "About Me", link: "About.vue" },
  { name: "Skill", link: "#skill" },
  { name: "Projects", link: "#portfolio" },
  { name: "Contact", link: "#contact" }
])
const isActive = ref(false)

function toggleActive() {
  isActive.value = !isActive.value
}
</script>
