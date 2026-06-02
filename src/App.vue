<script setup>
import { onMounted } from 'vue';
import gsap from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

const hoverCard = (event) => {
  gsap.to(event.currentTarget, { scale: 1.1, duration: 0.1, ease: "power2.out" });
};

const leaveCard = (event) => {
  gsap.to(event.currentTarget, { scale: 1, duration: 0.1, ease: "power2.out" });
};

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

  gsap.from("#sobre h2", {
    scrollTrigger: {
      trigger: "#sobre h2",
      start: "top 80%",
      toggleActions: "restart none none reverse",
    },
    opacity: 0,
    y: 50,
    duration: 1,
  });

  gsap.from("#sobre p", {
    scrollTrigger: {
      trigger: "#sobre p",
      start: "top 80%",
      toggleActions: "restart none none reverse",
    },
    opacity: 0,
    y: 80,
    duration: 1,
    ease: "power2.out",
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

  gsap.from("#contatos h2", {
    scrollTrigger: {
      trigger: "#contatos h2",
      start: "top 80%",
      toggleActions: "restart none none reverse",
    },
    opacity: 0,
    y: 50,
    duration: 1,
    ease: "power3.out",
  });

  gsap.from("#contatos li", {
    scrollTrigger: {
      trigger: "#contatos ul",
      start: "top 85%",
      toggleActions: "restart none none reverse",
    },
    opacity: 0,
    y: 100,
    duration: 0.8,
    stagger: 0.2,
    ease: "power2.out",
  });
});
</script>

<template>
  <div class="body">
    <header>
      <nav>
        <ul>
          <li><a href="#inicio">Inicio</a></li>
          <li><a href="#sobre">Sobre</a></li>
          <li><a href="#competencias">Competencias</a></li>
          <li><a href="#projetos">Projetos</a></li>
          <li><a href="#contatos">Contatos</a></li>
        </ul>
      </nav>
    </header>
    <main>
      <section id="inicio">
        <div class="inicio-container">
          <img src="/img/my-image.png" alt="Lucas Fontini">
          <h1>
            Olá, me chamo<br>Lucas <span>Fontini</span> da Luz
          </h1>
        </div>
      </section>

      <section id="sobre">
        <div class="section-container">
          <h2>Sobre <span>mim:</span></h2>
          <p>
            Sou estudante do IFC Araquari do curso de informática para internet, tenho 17 anos e sou apaixonado por tecnologia, principalmente desenvolvimento web. Estou sempre buscando aprender novas tecnologias e aprimorar minhas habilidades para me tornar um desenvolvedor cada vez melhor.
          </p>
        </div>
      </section>

      <section id="competencias">
        <div class="section-container">
          <h2>Minhas <span>competencias:</span></h2>
          <ul class="grid-competencias">
            <li class="card">
              <div class="img-wrapper"><img src="/img/Vue.png" alt="Vue logo"></div>
              <h3>Vue.js</h3>
            </li>
            <li class="card">
              <div class="img-wrapper"><img src="/img/HTML5_logo_and_wordmark.svg (1).png" alt="html logo"></div>
              <h3>HTML</h3>
            </li>
            <li class="card">
              <div class="img-wrapper"><img src="/img/CSS3_logo_and_wordmark.svg.png" alt="CSS logo"></div>
              <h3>CSS</h3>
            </li>
            <li class="card">
              <div class="img-wrapper"><img src="/img/JavaScript-logo.png" alt="JavaScript logo"></div>
              <h3>JavaScript</h3>
            </li>
            <li class="card">
              <div class="img-wrapper"><img src="/img/Figma-logo.svg.png" alt="Figma logo"></div>
              <h3>Figma</h3>
            </li>
            <li class="card">
              <div class="img-wrapper"><img style="color: white;" src="/img/Octicons-mark-github.svg" alt="GitHub logo"></div>
              <h3>Github</h3>
            </li>
            <li class="card">
              <div class="img-wrapper"><img src="/img/django.svg" alt="Django logo"></div>
              <h3>Django</h3>
            </li>
            <li class="card">
              <div class="img-wrapper"><img src="/img/pwa.svg" alt="PWA logo"></div>
              <h3>PWA</h3>
            </li>
            <li class="card">
              <div class="img-wrapper"><img src="/img/sql.png" alt="SQL logo"></div>
              <h3>SQL</h3>
            </li>
          </ul>
        </div>
      </section>

      <section id="projetos">
        <div class="section-container">
          <h2>Meus <span>Projetos:</span></h2>
          <ul class="grid-projetos">
            <li class="project">
              <img src="/img/rede.png" alt="Rede social">
              <a class="link" href="https://rede-social-institucional.surge.sh/" target="_blank" rel="noopener noreferrer">
                <h3>Rede social institucional</h3>
              </a>
              <p>
                <a class="git" href="https://github.com/Hackton2025/front-end" target="_blank" rel="noopener noreferrer">
                  <span class="mdi mdi-github"></span> Ver no GitHub
                </a>
              </p>
            </li>
            <li class="project">
              <img src="/img/robotica.png" alt="Robótica-IFC">
              <a class="link" href="https://robotica-ifc.vercel.app/" target="_blank" rel="noopener noreferrer">
                <h3>Robótica-IFC(em desenvolvimento)</h3>
              </a>
              <p>
                <a class="git" href="https://github.com/Robotica-IFC/Documentacao-PI" target="_blank" rel="noopener noreferrer">
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
                <a class="git" href="https://github.com/LucasFontini1/LFR" target="_blank" rel="noopener noreferrer">
                  <span class="mdi mdi-github"></span> Ver no GitHub
                </a>
              </p>
            </li>
          </ul>
        </div>
      </section>

      <section id="contatos">
        <div class="section-container">
          <h2>Entrar em <span>Contato:</span></h2>
          <ul class="grid-contatos">
            <li @mouseenter="hoverCard" @mouseleave="leaveCard">
              <a href="mailto:lucasfontinidaluz@gmail.com?subject=Contato&body=Olá%20Lucas," target="_blank" rel="noopener noreferrer">
                <img src="/img/Gmail_Icon.png" alt="Gmail">
              </a>
            </li>
            <li @mouseenter="hoverCard" @mouseleave="leaveCard">
              <a href="https://www.linkedin.com/in/lucas-fontini-da-luz-133a3b2b8" target="_blank" rel="noopener noreferrer">
                <img src="/img/LinkedIn_icon.svg.png" alt="LinkedIn">
              </a>
            </li>
            <li @mouseenter="hoverCard" @mouseleave="leaveCard">
              <a href="https://github.com/LucasFontini1" target="_blank" rel="noopener noreferrer">
                <img src="/img/Octicons-mark-github.svg" alt="GitHub">
              </a>
            </li>
            <li @mouseenter="hoverCard" @mouseleave="leaveCard">
              <a href="https://w.app/bxrgq4" target="_blank" rel="noopener noreferrer">
                <img src="/img/WhatsApp.svg.png" alt="WhatsApp">
              </a>
            </li>
          </ul>
        </div>
      </section>
    </main>
  </div>
</template>

<style scoped>
:global(html) {
  scroll-behavior: smooth;
}

.body {
  background-color: #37415c;
  min-height: 100vh;
  color: #e4e6ff;
  font-family: sans-serif;
  overflow-x: hidden;
}

h2 {
  text-align: center;
  font-size: 1.8rem;
  margin-bottom: 2rem;
}

h2 span {
  color: #b4182d;
}

header {
  position: sticky;
  top: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 10vh;
  width: 100%;
  background-color: #181a2fcc;
  backdrop-filter: blur(5px);
  z-index: 1000;
  padding: 0 1rem;
}

header nav ul {
  display: flex;
  gap: 1rem;
  list-style: none;
  flex-wrap: wrap;
  justify-content: center;
}

header nav ul li a {
  padding: 5px 8px;
  color: #e4e6ff;
  text-decoration: none;
  font-size: 0.9rem;
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

main section {
  width: 100%;
  min-height: 90vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 4rem 1rem;
}

.section-container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
}

#inicio .inicio-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 2rem;
  text-align: center;
  max-width: 1200px;
  width: 100%;
}

#inicio img {
  width: 150px;
  height: 150px;
  object-fit: cover;
  border-radius: 50%;
}

#inicio h1 {
  font-size: 1.8rem;
  font-family: 'Stack Sans Notch', sans-serif;
  line-height: 1.3;
}

#inicio h1 span {
  color: #b4182d;
}

#sobre p {
  text-align: center;
  width: 100%;
  max-width: 700px;
  font-size: 1.1rem;
  line-height: 1.6;
  margin: 0 auto;
}

.grid-competencias {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
  gap: 1.5rem;
  width: 100%;
  list-style: none;
  padding: 0;
}

#competencias ul li.card {
  background-color: #242e49;
  padding: 1.5rem 1rem;
  border-radius: 10px;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

#competencias .img-wrapper {
  width: 60px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 1rem;
}

#competencias ul li.card img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}

#competencias h3 {
  font-size: 1rem;
}

.grid-projetos {
  display: flex;
  flex-direction: column;
  gap: 2rem;
  width: 100%;
  list-style: none;
  padding: 0;
  align-items: center;
}

#projetos ul li {
  width: 100%;
  max-width: 450px;
  background-color: #242e49;
  padding: 1rem;
  border-radius: 8px;
}

#projetos ul li img {
  width: 100%;
  height: 200px;
  object-fit: cover;
  border-radius: 4px;
}

#projetos ul li a.link {
  text-decoration: none;
  color: #e4e6ff;
  display: flex;
  justify-content: center;
  margin-top: 1rem;
}

#projetos ul li a.link h3 {
  position: relative;
  display: inline-block;
  text-align: center;
  font-size: 1.1rem;
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

#projetos ul li a.link h3:hover::after {
  width: 100%;
}

#projetos ul li p {
  text-align: center;
  width: 100%;
}

#projetos ul li a.git {
  display: block;
  text-decoration: none;
  color: #e4e6ff;
  width: 100%;
  background-color: #181a2f;
  padding: 8px 10px;
  margin-top: 1rem;
  border-radius: 4px;
  transition: background 0.3s ease;
}

#projetos ul li a.git:hover {
  background-color: #10111b;
}

.grid-contatos {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1.5rem;
  width: 100%;
  max-width: 400px;
  list-style: none;
  padding: 0;
  margin: 0 auto;
}

#contatos ul li {
  background-color: #242e49;
  padding: 1.5rem;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
}

#contatos ul li a {
  width: 50px;
  height: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
}

#contatos ul li img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}

/* ==========================================================================
   MEDIA QUERIES (TABLETS - 600px até 768px)
   ========================================================================== */
@media (min-width: 600px) {
  header nav ul {
    gap: 1.5rem;
  }
  
  header nav ul li a {
    font-size: 1rem;
  }

  #inicio h1 {
    font-size: 2.2rem;
  }

  h2 {
    font-size: 2.2rem;
  }

  .grid-competencias {
    grid-template-columns: repeat(3, 1fr);
  }

  .grid-contatos {
    grid-template-columns: repeat(4, 1fr);
    max-width: 600px;
  }
}

/* ==========================================================================
   MEDIA QUERIES (NOTEBOOKS E LAPTOPS - 769px até 1024px)
   ========================================================================== */
@media (min-width: 769px) {
  #inicio .inicio-container {
    flex-direction: row;
    text-align: left;
    justify-content: center;
    gap: 3rem;
  }

  #inicio img {
    width: 220px;
    height: 220px;
  }

  #inicio h1 {
    font-size: 2.5rem;
  }

  .grid-competencias {
    grid-template-columns: repeat(6, 1fr);
  }

  .grid-projetos {
    flex-direction: row;
    justify-content: center;
    flex-wrap: wrap;
    gap: 2rem;
  }

  #projetos ul li {
    width: calc(50% - 1rem);
    max-width: 360px;
  }
}

/* ==========================================================================
   MEDIA QUERIES (DESKTOPS PADRÃO - 1025px até 1440px)
   ========================================================================== */
@media (min-width: 1025px) {
  header {
    height: 12vh;
  }

  header nav ul {
    gap: 2.5rem;
  }

  header nav ul li a {
    font-size: 1.1rem;
  }

  #inicio img {
    width: 250px;
    height: 250px;
  }

  #inicio h1 {
    font-size: 3rem;
  }

  #sobre p {
    font-size: 1.25rem;
    max-width: 850px;
  }

  #projetos ul li {
    max-width: 380px;
  }
}

/* ==========================================================================
   MEDIA QUERIES (TELAS GRANDES E ULTRAWIDE - Acima de 1441px)
   ========================================================================== */
@media (min-width: 1441px) {
  .section-container {
    max-width: 1400px;
  }

  #inicio h1 {
    font-size: 3.8rem;
  }

  #inicio img {
    width: 300px;
    height: 300px;
  }

  h2 {
    font-size: 2.8rem;
    margin-bottom: 3.5rem;
  }

  #sobre p {
    font-size: 1.4rem;
    max-width: 1000px;
  }

  #projetos ul li {
    max-width: 420px;
  }

  #competencias .img-wrapper {
    width: 80px;
    height: 80px;
  }

  #competencias h3 {
    font-size: 1.2rem;
  }
}
</style>