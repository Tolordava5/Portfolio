<template>
    <div class="contact">
        <!-- first div -->
        <div class="info">
            <h2>Contact <b>Me</b></h2>
            <span>Letss Work together</span>
            <p>Thank you for visiting my personal portfolio website! If you have any questions, suggestions, or would
                like to collaborate, feel free to reach out using this form. I'll do my best to respond to your message
                as soon as possible</p>
            <!-- first div -->
            <div>
                <div>
                    <img src="../assets/Photos/sendd.png" alt="">
                    <p><B>georgertolordava5@gmail.com</B></p>
                </div>
                <div>
                    <img src="../assets/Photos/call.png" alt="">
                    <p><B>(+995) 571-218-901</B></p>
                </div>
            </div>
            <!-- last div -->
            <div>
                <a href="https://www.facebook.com/giorgi.tolordava.576786"><img src="../assets//Photos/facebook.png"
                        alt=""></a>
                <a href="https://www.instagram.com/georgetolordava5/"><img src="../assets/Photos/instagram.webp"
                        alt=""></a>
                <a href="https://github.com/Tolordava5"><img src="../assets/Photos/github.png" alt=""></a>
                <a href="https://www.linkedin.com/in/george-george-629411258/"><img src="../assets/Photos/linkdin.png"
                        alt=""></a>
            </div>
        </div>
        <div>
            <input type="text" placeholder="Enter Your Name">
            <input type="text" placeholder="Enter Your Email">
            <input type="text" placeholder="Enter Your Subject">
            <textarea placeholder="Enter Your Message"></textarea>
            <button>Submit</button>

        </div>
    </div>
</template>
<style scoped>
.contact {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 30px;
    height: 700px;
    background: linear-gradient(to left, #161616, #1a1128);
    color: white;
    border-top: 1px solid white;
    font-size: 21px;
    padding-left: 200px;
}

.info {
    display: flex;
    flex-direction: column;
    gap: 30px;

}

.info h2 {
    font-size: 72px;
    display: flex;
    gap: 10px;
    justify-content: center;
}

.info h2 b {
    color: #a259ff;
    text-shadow: 0 0 4px #A259FF, 0 0 8px #A259FF;
}

.info p {
    width: 600px;
}

.info div:first-child {
    display: flex;
    align-items: center;
    gap: 20px;

}

.info div img {
    display: flex;
    width: 50px;

}

.info div:last-child {
    display: flex;
    align-items: center;
    gap: 20px;
    margin-top: 20px;

}

.contact>div:last-child {
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: 15px;
}

.contact>div:last-child input {
    width: 400px;
    height: 61px;
    border-radius: 12px;
    border: none;
    padding: 20px;
    display: flex;
    background-color: rgba(255, 255, 255, 0.082);
    color: white;
}

.contact>div:last-child button {
    background-color: #A259FF;
    border: none;
    border-radius: 12px;
    width: 200px;
    height: 51px;
    cursor: pointer;
    margin-top: 30px;
    transition: 0.6s;
}
.contact > div:last-child textarea {
    width: 400px;
    height: 140px;
    border-radius: 12px;
    border: none;
    padding: 20px;
    background-color: rgba(255, 255, 255, 0.082);
    color: white;
    resize: none;
    font-family: inherit;
    font-size: 16px;
}

.contact button:hover {
    box-shadow: 0 0 10px #A259FF, 0 0 20px #A259FF;

}
</style>