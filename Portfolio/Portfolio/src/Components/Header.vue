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
h3{
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
</script>
