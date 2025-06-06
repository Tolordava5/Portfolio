<template>
  <div class="inforamtion">
    <!-- first child -->
    <div>
      <div>
        <h3>Hello, I'm</h3>
        <h1>Giorgi Tolordava</h1>
        <h2 id="autoWriter">And i am Web Developer...</h2>
      </div>
      <div class="social">
        <a href="https://www.facebook.com/giorgi.tolordava.576786"><img src="../assets//Photos/facebook.png" alt=""></a>
        <a href="https://www.instagram.com/georgetolordava5/"><img src="../assets/Photos/instagram.webp" alt=""></a>
        <a href="https://github.com/Tolordava5"><img src="../assets/Photos/github.png" alt=""></a>
        <a href="https://www.linkedin.com/in/george-george-629411258/"><img src="../assets/Photos/linkdin.png"
            alt=""></a>
        <div class="btns">
          <a href="About.vue"><button>More about me</button></a>
          <a href="Giorgi-Tolordava.pdf"><button>CV</button></a>
        </div>
      </div>
    </div>
    <!-- last child -->
    <div>
      <img src="../assets/Photos/George.jpg" alt="">
    </div>
  </div>
</template>

<style scoped>
h3 {
  font-size: 40px;
}

h1 {
  font-size: 50px;
}

.inforamtion {
  color: white;
  display: grid;
  grid-template-columns: 1fr 1fr;
  background: linear-gradient(to left, #161616, #1a1128);
}

.inforamtion div:first-child img {
  width: 50px;
  margin-right: 30px;
}

.inforamtion div:first-child {
  display: flex;
  flex-direction: column;
  justify-content: center;
  margin: 0 auto;
  gap: 15px;
  width: 400px;

}

.inforamtion h2 {
  font-size: 42px;
}

.inforamtion>div:last-child img {
  width: 500px;
  border-radius: 50%;
  margin-top: 50px;
  margin-left: 100px;
}

#autoWriter {
  font-size: 32px;
  color: white;
  white-space: nowrap;
  overflow: hidden;
  border-right: 2px solid #A259FF;
  width: fit-content;
}
.btns{
  display: flex;
  gap: 30px;
}
.btns > a:first-child > button{
  background-color: #A259FF;
  border: none;
  border-radius: 12px;
  width: 160px;
  height: 51px;
  cursor: pointer;
  margin-top: 30px;
  transition: 0.6s;
}

.btns > a:last-child > button {
  background: transparent;
  border:  1px solid #A259FF;
  width: 160px;
  height: 51px;
  border-radius: 12px;
  transition: 0.6s;
  margin-top: 30px;
  color: white;
  cursor: pointer;


}

.social button:hover {
  box-shadow: 0 0 10px #A259FF, 0 0 20px #A259FF;
}
@media  screen and (max-width:600px) {
  .inforamtion{
    display: flex;
    flex-direction: column-reverse;
  }
.inforamtion > div:last-child> img {
  width: 350px;
  margin: 0 auto;
  padding: 5px;
  margin-left: 2px;
  margin-top: 10px;
}
.inforamtion div{
  padding: 10px;
}
.inforamtion h1{
  font-size: 40px;
}
  .inforamtion h3{
  font-size: 30px;
}
#autoWriter {
  font-size: 30px;
  color: white;
  white-space: nowrap;
  overflow: hidden;
  border-right: 2px solid #A259FF;
  width: fit-content;
}
.btns {
  width: 30px;
  gap: 10px ;
}
}
</style>
<script setup>
import { onMounted } from 'vue'
onMounted(() => {
  const element = document.getElementById('autoWriter');
  const text = "And i am Web Developer...";
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