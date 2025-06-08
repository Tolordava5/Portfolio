<template>
  <div class="about">
    <div>
      <img src="../assets/Photos/coding.avif" alt="Coding image">
    </div>
    <div>
      <h2>About <b>Me</b></h2>
      <span>Giorgi Tolordava</span>
      <p>
        {{ shortText }}
        <span v-if="showMore">{{ remainingText }}</span>
      </p>
      <button @click="toggleText" class="read-more-btn">
        {{ showMore ? 'Less' : 'More' }}
      </button>
    </div>
  </div>
</template>



<style scoped>
.about {
  background: linear-gradient(to left, #161616, #1a1128);
  color: white;
  display: grid;
  grid-template-columns: 1fr 1fr;
  padding-top: 150px;
  padding-left: 30px;
  padding-right: 30px;
  gap: 40px;
  align-items: center;
}

.about img {
  border-radius: 50%;
  height: 500px;
  width: 550px;
  display: flex;
  margin: 0 auto;
  object-fit: cover;
}

.about div:last-child {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.about h2 {
  font-size: 46px;
}

.about b {
  color: #a259ff;
  text-shadow: 0 0 4px #A259FF, 0 0 8px #A259FF;
}

.about span {
  font-size: 21px;
}

.about p {
  max-width: 760px;
  width: 100%;
  font-size: 21px;
  font-family: 'Courier New', Courier, monospace;
  line-height: 1.6;
  color: white;
}

.read-more-btn {
  background: none;
  border: none;
  color: #a259ff;
  font-weight: bold;
  cursor: pointer;
  padding-left: 0;
  font-size: 16px;
  align-self: flex-start;
}

@media screen and (max-width: 600px) {
  .about {
    flex-direction: column;
    display: flex;
    padding: 40px 20px;
    gap: 40px;
  }

  .about img {
    width: 350px;
    height: 330px;
    margin: 0 auto;
  }

  .about div:last-child {
    padding-left: 0;
  }

  .about p {
    max-width: 100%;
    width: 100%;
  }
}
</style>
<script>
export default {
  data() {
    return {
      showMore: false,
      fullText: `I'm a 20-year-old Front-End Developer with a strong passion for building modern user-focused web
        experiences. With a solid foundation in HTML, CSS, JavaScript, and modern frameworks like React and Vue,
        I specialize in crafting responsive, accessible, and visually engaging interfaces. My toolkit also includes
        Tailwind and TypeScript, which allow me to write scalable and maintainable code efficiently.
        I'm continuously evolving as a developer, staying up to date with the latest trends in frontend
        development and best practices. I thrive in environments where I can grow my skill set, collaborate with others, and
        contribute to the development of performant and scalable web applications.
        My ultimate goal is to play an active role in creating systems that not only solve real-world problems but
        also enhance overall user satisfaction and company productivity. Whether working independently or as
        part of a team, I bring a strong sense of ownership, a keen eye for detail, and a deep commitment to delivering
        high-quality digital solutions.`
    };
  },
  computed: {
    shortText() {
      return this.fullText.slice(0, 300) + (this.showMore ? '' : '...');
    },
    remainingText() {
      return this.fullText.slice(300);
    }
  },
  methods: {
    toggleText() {
      this.showMore = !this.showMore;
    }
  }
};
</script>