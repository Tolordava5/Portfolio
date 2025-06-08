<template>
  <div class="information">
    <!-- Left Side -->
    <div class="text-content">
      <div>
        <h3>Hello, I'm</h3>
        <h1>Giorgi Tolordava</h1>
        <h2 id="autoWriter">And I am Web Developer...</h2>
      </div>
      <div class="social">
        <a href="https://www.facebook.com/giorgi.tolordava.576786" target="_blank">
          <img src="../assets/Photos/facebook.png" alt="Facebook">
        </a>
        <a href="https://www.instagram.com/georgetolordava5/" target="_blank">
          <img src="../assets/Photos/instagram.webp" alt="Instagram">
        </a>
        <a href="https://github.com/Tolordava5" target="_blank">
          <img src="../assets/Photos/github.png" alt="GitHub">
        </a>
        <a href="https://www.linkedin.com/in/george-george-629411258/" target="_blank">
          <img src="../assets/Photos/linkdin.png" alt="LinkedIn">
        </a>
      </div>
      <div class="btns">
        <a href="About.vue"><button class="primary-btn">More about me</button></a>
        <a href="Giorgi-Tolordava.pdf"><button class="secondary-btn">CV</button></a>
      </div>
    </div>

    <!-- Right Side -->
    <div class="image-section">
      <img src="../assets/Photos/George.jpg" alt="Giorgi Tolordava">
    </div>
  </div>
</template>



<style scoped>
.information {
  color: white;
  display: grid;
  grid-template-columns: 1fr 1fr;
  background: linear-gradient(to left, #161616, #1a1128);
  align-items: center;
  padding: 50px 30px;
}

.text-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 20px;
  width: 100%;
  max-width: 500px;
  margin: 0 auto;
}

h3 {
  font-size: 40px;
}

h1 {
  font-size: 50px;
}

h2#autoWriter {
  font-size: 32px;
  color: white;
  white-space: nowrap;
  overflow: hidden;
  border-right: 2px solid #A259FF;
  width: fit-content;
}

.social {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-top: 10px;
}

.social img {
  width: 40px;
  transition: transform 0.3s;
}

.social img:hover {
  transform: scale(1.2);
}

.btns {
  display: flex;
  gap: 20px;
  margin-top: 30px;
}

.primary-btn {
  background-color: #A259FF;
  color: white;
  border: none;
  border-radius: 12px;
  width: 160px;
  height: 51px;
  cursor: pointer;
  transition: 0.4s;
}

.secondary-btn {
  background: transparent;
  border: 1px solid #A259FF;
  color: white;
  width: 160px;
  height: 51px;
  border-radius: 12px;
  cursor: pointer;
  transition: 0.4s;
}

.primary-btn:hover,
.secondary-btn:hover {
  box-shadow: 0 0 10px #A259FF, 0 0 20px #A259FF;
}

.image-section img {
  width: 500px;
  border-radius: 50%;
  object-fit: cover;
  margin: 0 auto;
  display: block;
  margin-top: 50px;
}

@media screen and (max-width: 600px) {
  .information {
    display: flex;
    flex-direction: column-reverse;
    padding: 30px 15px;
    gap: 40px;
  }

  h1 {
    font-size: 36px;
  }

  h3 {
    font-size: 28px;
  }

  h2#autoWriter {
    font-size: 26px;
  }

  .image-section img {
    width: 320px;
    margin-top: 10px;
  }

  .btns {
    flex-direction: column;
    gap: 15px;
  }

  .primary-btn,
  .secondary-btn {
    width: 100%;
  }
}
</style>
<script setup>
import { onMounted } from 'vue';

onMounted(() => {
  const element = document.getElementById('autoWriter');
  const text = "And I am Web Developer...";
  let index = 1;
  let isDeleting = false;

  function type() {
    if (!element) return;

    if (!isDeleting) {
      element.textContent = text.substring(0, index++);
      if (index > text.length) {
        isDeleting = true;
        setTimeout(type, 1000);
        return;
      }
    } else {
      index--;
      if (index < 2) {
        isDeleting = false;
      }
      element.textContent = text.substring(0, index);
    }
    setTimeout(type, isDeleting ? 70 : 120);
  }

  type();
});
</script>