<template>
    <div class="about">
        <div>
            <img src="../assets/Photos/coding.avif" alt="">
        </div>
        <div>
            <h2>About <b>Me</b></h2>
            <span>Giorgi Tolordava</span>
            <p>I'm a 20-year-old Front-End Developer with a strong passion for building modern, user-focused web
                experiences. With a solid foundation in HTML, CSS, JavaScript, and modern frameworks like React and Vue,
                I
                specialize in crafting responsive, accessible, and visually engaging interfaces. My toolkit also
                includes
                Tailwind and TypeScript, which allow me to write scalable and maintainable code efficiently. <br>

                I'm continuously evolving as a developer, staying up to date with the latest trends in frontend
                development
                and best practices. I thrive in environments where I can grow my skill set, collaborate with others, and
                contribute to the development of performant and scalable web applications. <br>

                My ultimate goal is to play an active role in creating systems that not only solve real-world problems
                but
                also enhance overall user satisfaction and company productivity. Whether working independently or as
                part of
                a team, I bring a strong sense of ownership, a keen eye for detail, and a deep commitment to delivering
                high-quality digital solutions.</p>
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
}
.about img{
    border-radius: 50%;
    height: 500px;
    width: 550px;
    display: flex;
    margin: 0 auto;
    margin-top: 100px;
}
.about div:last-child{
    display: flex;
    flex-direction: column;
    gap: 30px;
}
.about h2{
    font-size: 46px;
}
.about b{
    color: #a259ff;
    text-shadow: 0 0 4px #A259FF, 0 0 8px #A259FF;
}
.about span{
    font-size: 21px;
}
.about p{
    width: 760px;
    font-size:21px;
    display: flex;
    font-family: 'Courier New', Courier, monospace;
}
</style>