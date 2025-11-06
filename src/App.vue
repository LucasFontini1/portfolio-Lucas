<script setup>
import { onMounted } from 'vue';

import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);


  onMounted(() => {
  gsap.from("#inicio img", {
    opacity: 0,
    x: -50,
    duration: 1.2,
    ease: "power3.out",
  });

  gsap.from("#inicio h1", {
    opacity: 0,
    x: 50,
    duration: 1.2,
    ease: "power3.out",
  });

  gsap.from("#competencias h2", {
    scrollTrigger: {
      trigger: "#competencias h2",
      start: "top 80%",
      toggleActions: "restart none none reverse",
    },
    opacity: 0,
    y: 50,
    duration: 1,
  });

  gsap.from("#competencias .card", {
    scrollTrigger: {
      trigger: "#competencias",
      start: "top 70%",
      toggleActions: "restart none none reverse",
    },
    opacity: 0,
    y: 80,
    duration: 0.8,
    stagger: 0.15,
    ease: "power2.out",
  });

  gsap.from("#projetos h2", {
    scrollTrigger: {
      trigger: "#projetos h2",
      start: "top 80%",
      toggleActions: "restart none none reverse",
    },
    opacity: 0,
    y: 60,
    duration: 1,
  });

  gsap.from("#projetos .project", {
    scrollTrigger: {
      trigger: "#projetos ul",
      start: "top 80%",
      toggleActions: "restart none none reverse",
    },
    opacity: 0,
    y: 100,
    duration: 1,
    stagger: 0.2,
    ease: "power3.out"
  });

  gsap.from("#projetos .git", {
    scrollTrigger: {
      trigger: "#projetos",
      start: "top 90%",
      toggleActions: "restart none none reverse",
    },
    opacity: 0,
    scale: 0.8,
    duration: 0.6,
    stagger: 0.15,
    ease: "back.out(1.7)",
  });
});
</script>
<template>
  <div class="body">
    <header>
      <nav>
        <ul>
          <li><a href="#inicio">Inicio</a></li>
          <li><a href="#competencias">Competencias</a></li>
          <li><a href="#projetos">Projetos</a></li>
          <li><a href="">Contatos</a></li>
        </ul>
      </nav>
    </header>
    <main>
      <section id="inicio">
        <img src="/img/my-image.png" alt="">
        <h1>
          Olá, me chamo<br>Lucas <span>Fontini</span> da Luz
        </h1>
      </section>
      <section id="competencias">
        <div>
          <h2>Minhas <span>competencias:</span></h2>
          <ul>
            <li class="card">
              <img src="/img/Vue.png" alt="Vue logo">
              <h3>
                Vue.js
              </h3>
            </li>
            <li class="card">
              <img src="/img/HTML5_logo_and_wordmark.svg (1).png" alt="html logo">
              <h3>
                HTML
              </h3>
            </li>
            <li class="card">
              <img src="/img/CSS3_logo_and_wordmark.svg.png" alt="">
              <h3>
                CSS
              </h3>
            </li>
            <li class="card">
              <img src="/img/JavaScript-logo.png" alt="JavaScript logo">
              <h3>
                JavaScript
              </h3>
            </li>
            <li class="card">
              <img src="/img/Figma-logo.svg.png" alt="Figma logo">
              <h3>Figma</h3>
            </li>
            <li class="card">
              <img style="color: white;" src="/img/Octicons-mark-github.svg" alt="">
              <h3>Github</h3>
            </li>
          </ul>
        </div>
      </section>
      <section id="projetos">
        <div>
        <h2>Meus <span>Projetos:</span></h2>
        <ul>
          <li class="project">
            <img src="/img/rede.png" alt="Rede social">
            <a class="link" href="https://rede-social-institucional.surge.sh/" target="_blank"
              rel="noopener noreferrer">
              <h3>Rede social institucional</h3>
            </a>
            <p>
              <a class="git" href="https://github.com/Hackton2025/front-end" target="_blank" rel="noopener noreferrer">
                <span class="mdi mdi-github"></span> Ver no GitHub
              </a>
            </p>
          </li>

          <li class="project">
            <img src="/img/gues.png" alt="Advinhe a bandeira">
            <a class="link" href="https://advinhe-a-bandeira.vercel.app/" target="_blank" rel="noopener noreferrer">
              <h3>Advinhe a bandeira</h3>
            </a>
            <p>
              <a class="git" href="https://github.com/LucasFontini1/LFR" target="_blank" rel="noopener noreferrer">
                <span class="mdi mdi-github"></span> Ver no GitHub
              </a>
            </p>
          </li>

          <li class="project">
            <img src="/img/lfr.png" alt="Games LFR">
            <a class="link" href="https://lfr-smoky.vercel.app/" target="_blank" rel="noopener noreferrer">
              <h3>Games LFR</h3>
            </a>
            <p>
              <a class="git" href="https://github.com/LucasFontini1/Advinhe-a-bandeira" target="_blank" rel="noopener noreferrer">
                <span class="mdi mdi-github"></span> Ver no GitHub
              </a>
            </p>
          </li>
        </ul>
        </div>
      </section>


    </main>
  </div>
</template>

<style scoped>
.body {
  background-color: #37415c;
  min-height: 100vh;
  color: #e4e6ff;
  font-family: sans-serif;
}

header {
  position: sticky;
  top: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 15vh;
  width: 100%;
  background-color: #181a2f70;
  z-index: 1000;
}

header nav ul {
  display: flex;
  gap: 2rem;
  list-style: none;
}

header nav ul li a {
  padding: 5px 10px;
  color: #e4e6ff;
  text-decoration: none;
  font-size: 1.2rem;
  position: relative;
}

header nav ul li a::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  width: 0%;
  height: 2px;
  background-color: #b4182d;
  transition: width 0.3s ease;
}

header nav ul li a:hover::after {
  width: 100%;
}

#inicio {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 85vh;
  gap: 1rem;
}

#inicio img {
  width: 20%;
  border-radius: 50%;
}

#inicio h1 {
  font-size: 2.5rem;
  font-family: 'Stack Sans Notch', sans-serif;
}

#inicio h1 span {
  color: #b4182d;
}

#competencias {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

#competencias h2 {
  font-size: 2rem;
  text-align: center;
  margin-bottom: 1rem;
}

#competencias h2 span {
  color: #b4182d;
}

#competencias ul {
  display: flex;
  list-style: none;
  gap: 2rem;
  width: 80%;
  justify-content: center;
  margin: 0 auto;
}

#competencias ul li.card {
  background-color: #242e49;
  padding: 1rem;
  width: 30%;
  border-radius: 10px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  position: relative;
}

#competencias ul li.card img {
  width: 20vh;
  height: 20vh;
  display: flex;
  margin-bottom: 1rem;
}
#projetos{
  width: 100%;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
#projetos h2{
  text-align: center;
  font-size: 2rem;
}
#projetos h2 span{
  color: #b4182d;
}
#projetos ul{
  display: flex;
  width: 80%;
  justify-content: center;
  align-items: center;
  margin: 0 auto;
  list-style: none;
  gap: 1rem;
}
#projetos ul li{
  width: 40%;
  position: relative;
  background-color: #242e49;
  padding: 1rem;
}
#projetos ul li img{
  width: 100%;
}
#projetos ul li a.link{
  text-decoration: none;
  color: #e4e6ff;
  display: flex;
  justify-content: center;
}
#projetos ul li a.link h3{
  position: relative;
  display: inline-block;
  text-align: center;
  font-size: 1.2rem;
}
#projetos ul li a.link h3::after {
  content: '';
  position: absolute;
  bottom: 0; 
  left: 0;
  width: 0%;
  height: 2px;
  background-color: #b4182d;
  transition: width 0.3s ease;
}
#projetos ul li a.link h3:hover::after{
  width: 100%;
}
#projetos ul li p{
  text-align: center;
  width: 100%;
}
#projetos ul li a.git{
  display: block;
  text-decoration: none;
  color: #e4e6ff;
  width: 100%;
    background-color: #181a2f;
    padding: 5px 10px;margin-top: 1rem;
    transition: background 0.3s ease;
}
#projetos ul li a.git:hover{
  background-color: #10111b;
}
</style>
