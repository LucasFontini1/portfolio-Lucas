<script setup>
import { onMounted, onUnmounted, ref } from 'vue';

const menuOpen = ref(false);
const year = new Date().getFullYear();
let gsapContext;
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
  if (window.matchMedia('(prefers-reduced-motion: reduce)').matches) return;
  gsapContext = gsap.context(() => {
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
});
onUnmounted(() => gsapContext?.revert());
</script>

<template>
  <div class="body">
    <header>
      <button class="menu-toggle" type="button" @click="menuOpen = !menuOpen" :aria-expanded="menuOpen" aria-controls="main-navigation" aria-label="Abrir ou fechar menu"><span class="mdi mdi-menu"></span> Menu</button>
      <nav id="main-navigation" :class="{ 'menu-open': menuOpen }" aria-label="Navegação principal">
        <ul @click="menuOpen = false">
          <li><a href="#inicio">Inicio</a></li>
          <li><a href="#sobre">Sobre</a></li>
          <li><a href="#competencias">Competências</a></li>
          <li><a href="#formacao">Formação</a></li>
          <li><a href="#projetos">Projetos</a></li>
          <li><a href="#contatos">Contatos</a></li>
        </ul>
      </nav>
    </header>
    <main>
      <section id="inicio">
        <div class="inicio-container">
          <img src="/img/my-image.png" alt="Foto de Lucas Fontini da Luz" width="300" height="300">
          <div class="hero-copy"><p class="eyebrow">Olá, seja bem-vindo ao meu portfólio</p><h1>Lucas <span>Fontini</span> da Luz</h1><p class="hero-subtitle">Desenvolvedor Web · Frontend e Backend</p><p>Estudante de Informática para Internet no IFC Campus Araquari, apaixonado por criar soluções digitais.</p><div class="hero-actions"><a class="btn-primary" href="#projetos">Conhecer projetos <span aria-hidden="true">↗</span></a><a class="btn-outline" href="#contatos">Entrar em contato</a></div><p class="resume-note">Currículo em PDF: disponível mediante solicitação por e-mail.</p></div>
        </div>
      </section>

      <section id="sobre">
        <div class="section-container">
          <h2>Sobre <span>mim:</span></h2>
          <p>
            Sou estudante de Informática para Internet no Instituto Federal Catarinense (IFC), Campus Araquari. Tenho interesse em desenvolvimento frontend e backend, banco de dados e design de interfaces. Participo de projetos e hackathons para transformar o que aprendo em aplicações reais.
          </p>
        </div>
      </section>

      <section id="competencias">
        <div class="section-container">
          <h2>Minhas <span>competencias:</span></h2>
          <div class="skills-groups">
            <div class="skill-group"><h3><span class="mdi mdi-monitor"></span> Frontend</h3><ul><li>Vue.js</li><li>JavaScript</li><li>HTML5</li><li>CSS3</li><li>PWA</li></ul></div>
            <div class="skill-group"><h3><span class="mdi mdi-server"></span> Backend</h3><ul><li>Django</li><li>Desenvolvimento de APIs</li></ul></div>
            <div class="skill-group"><h3><span class="mdi mdi-database"></span> Dados</h3><ul><li>SQL</li><li>Banco de dados</li></ul></div>
            <div class="skill-group"><h3><span class="mdi mdi-tools"></span> Ferramentas e design</h3><ul><li>GitHub</li><li>Figma</li></ul></div>
          </div>
        </div>
      </section>

      <section id="formacao"><div class="section-container"><h2>Formação <span>& experiências:</span></h2><div class="journey-grid"><article class="journey-card"><span class="mdi mdi-school-outline" aria-hidden="true"></span><h3>Instituto Federal Catarinense</h3><p>Campus Araquari · Curso de Informática para Internet</p><span class="small-tag">Formação acadêmica</span></article><article class="journey-card"><span class="mdi mdi-trophy-outline" aria-hidden="true"></span><h3>Hackathons e projetos</h3><p>Participação em projetos de desenvolvimento web, incluindo o Momentum no Hackathon IFC 2026 e uma rede social institucional.</p><span class="small-tag">Aprendizado na prática</span></article></div></div></section>

      <section id="projetos">
        <div class="section-container">
          <h2>Meus <span>Projetos:</span></h2><p class="section-lead">Aplicações e experiências desenvolvidas durante minha formação. Explore os sites e o código-fonte.</p>
          <ul class="grid-projetos">
            <li class="project">
              <img src="/img/rede.png" alt="Prévia da rede social institucional" loading="lazy">
              <a class="link" href="https://rede-social-institucional.surge.sh/" target="_blank" rel="noopener noreferrer">
                <h3>Rede social institucional</h3>
              </a>
              <p class="project-description">Projeto de rede social institucional desenvolvido em equipe.</p><div class="project-tags"><span>Frontend</span><span>Projeto em equipe</span></div>
              <p>
                <a class="git" href="https://github.com/Hackton2025/front-end" target="_blank" rel="noopener noreferrer">
                  <span class="mdi mdi-github"></span> Ver no GitHub
                </a>
              </p>
            </li>
            <li class="project">
              <img src="/img/robotica.png" alt="Prévia do projeto Robótica IFC" loading="lazy">
              <a class="link" href="https://robotica-ifc.vercel.app/" target="_blank" rel="noopener noreferrer">
                <h3>Robótica IFC <small>· em desenvolvimento</small></h3>
              </a>
              <p class="project-description">Site do projeto Robótica IFC, em desenvolvimento.</p><div class="project-tags"><span>Web</span><span>Em desenvolvimento</span></div>
              <p>
                <a class="git" href="https://github.com/Robotica-IFC/Documentacao-PI" target="_blank" rel="noopener noreferrer">
                  <span class="mdi mdi-github"></span> Ver no GitHub
                </a>
              </p>
            </li>
            <li class="project">
              <img src="/img/lfr.png" alt="Prévia do projeto Games LFR" loading="lazy">
              <a class="link" href="https://lfr-smoky.vercel.app/" target="_blank" rel="noopener noreferrer">
                <h3>Games LFR</h3>
              </a>
              <p class="project-description">Projeto Games LFR, disponível para conhecer online.</p><div class="project-tags"><span>Web</span><span>Projeto pessoal</span></div>
              <p>
                <a class="git" href="https://github.com/LucasFontini1/LFR" target="_blank" rel="noopener noreferrer">
                  <span class="mdi mdi-github"></span> Ver no GitHub
                </a>
              </p>
            </li>
            <li class="project">
              <div class="momentum-preview" role="img" aria-label="Identidade visual do projeto Momentum">
                <span class="momentum-mark">M</span>
                <span class="momentum-name">Momentum</span>
                <span class="momentum-caption">Hackathon IFC 2026</span>
              </div>
              <a class="link" href="https://momentum-sable-seven.vercel.app/" target="_blank" rel="noopener noreferrer">
                <h3>Momentum</h3>
              </a>
              <p class="project-description">Aplicação web desenvolvida no Hackathon IFC 2026, com frontend e backend em repositórios separados.</p><div class="project-tags"><span>Hackathon 2026</span><span>Full Stack</span></div>
              <p>
                <a class="git" href="https://github.com/Hackaton-2026-IFC/Frontend-Hackathon" target="_blank" rel="noopener noreferrer">
                  <span class="mdi mdi-github"></span> Frontend no GitHub
                </a>
                <a class="git" href="https://github.com/Hackaton-2026-IFC/Backend-Hackathon" target="_blank" rel="noopener noreferrer">
                  <span class="mdi mdi-github"></span> Backend no GitHub
                </a>
              </p>
            </li>
          </ul>
        </div>
      </section>

      <section id="contatos">
        <div class="section-container">
          <h2>Entrar em <span>Contato:</span></h2><p class="section-lead">Tem uma oportunidade, ideia ou projeto? Vamos conversar!</p><a class="btn-primary contact-cta" href="mailto:lucasfontinidaluz@gmail.com?subject=Contato%20pelo%20portfolio">Enviar e-mail <span aria-hidden="true">↗</span></a>
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
    <footer><p>© {{ year }} Lucas Fontini da Luz · Feito com Vue.js</p><a href="#inicio">Voltar ao topo ↑</a></footer>
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
.momentum-preview {
  width: 100%;
  height: 200px;
  border-radius: 4px;
  background: linear-gradient(135deg, #111827 0%, #2f3f68 100%);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 0.45rem;
  text-align: center;
  padding: 1rem;
}
.momentum-mark {
  display: grid;
  place-items: center;
  width: 58px;
  height: 58px;
  border-radius: 16px;
  background: #e4e6ff;
  color: #202942;
  font-size: 2rem;
  font-weight: 800;
}
.momentum-name { font-size: 1.45rem; font-weight: 700; }
.momentum-caption { font-size: 0.78rem; opacity: 0.85; }

/* Atualização de acessibilidade, identidade visual e responsividade */
:global(*) { box-sizing: border-box; }
:global(body) { margin: 0; }
:global(:focus-visible) { outline: 3px solid #ffb4bf; outline-offset: 4px; }
:global(html) { scroll-padding-top: 90px; }
.body { line-height: 1.6; }
header { min-height: 74px; height: auto; padding: 12px 1rem; }
.menu-toggle { display: none; color: #e4e6ff; background: transparent; border: 1px solid #8991af; border-radius: 9px; padding: 8px 15px; cursor: pointer; font: inherit; }
main section { min-height: auto; padding: clamp(5rem, 8vw, 8rem) 1.25rem; scroll-margin-top: 75px; }
#inicio { min-height: calc(100svh - 75px); }
#inicio .inicio-container { max-width: 1100px; }
.hero-copy { max-width: 650px; }
#inicio h1 { line-height: 1.12; margin: 0.3rem 0 1rem; }
.eyebrow { letter-spacing: .07em; color: #ffb0be; font-weight: 700; }
.hero-subtitle { font-size: clamp(1.15rem,2vw,1.5rem); font-weight: 700; }
.hero-actions { display:flex; flex-wrap:wrap; gap:.85rem; margin-top:1.5rem; }
.btn-primary,.btn-outline { display:inline-flex; align-items:center; justify-content:center; gap:.7rem; text-decoration:none; padding:.85rem 1.3rem; border-radius:9px; font-weight:700; transition:transform .2s ease, background-color .2s ease; }
.btn-primary { background:#b4182d; color:white; }
.btn-outline { border:1px solid #b5bad8; color:#e4e6ff; }
.btn-primary:hover,.btn-outline:hover { transform:translateY(-3px); }
.resume-note { font-size:.85rem; opacity:.78; margin-top:1rem; }
.section-lead { max-width:650px; text-align:center; margin:0 auto 2rem; opacity:.9; }
.skills-groups,.journey-grid { display:grid; grid-template-columns:repeat(2,minmax(0,1fr)); gap:1.5rem; max-width:1000px; margin:auto; }
.skill-group,.journey-card { background:#242e49; border:1px solid #596583; border-radius:13px; padding:1.8rem; }
.skill-group h3 { margin:0 0 1.2rem; color:#ffb0be; }
.skill-group h3 .mdi { margin-right:.4rem; }
.skill-group ul { display:flex; flex-wrap:wrap; gap:.65rem; padding:0; margin:0; list-style:none; }
.skill-group li,.project-tags span,.small-tag { border:1px solid #7b86a6; border-radius:100px; padding:.35rem .8rem; font-size:.9rem; background:#37415c; }
.journey-card > .mdi { font-size:2rem; color:#ffb0be; }
.journey-card h3 { margin:.5rem 0; }
.small-tag { display:inline-block; margin-top:1rem; }
.grid-projetos { display:grid; grid-template-columns:repeat(2,minmax(0,1fr)); gap:1.5rem; align-items:stretch; max-width:1100px; margin:auto; }
#projetos ul li.project { width:100%; max-width:none; display:flex; flex-direction:column; padding:1.2rem; border:1px solid #596583; border-radius:14px; box-shadow:0 8px 28px #13162935; transition:transform .25s ease,border-color .25s ease; }
#projetos ul li.project:hover { transform:translateY(-5px); border-color:#b8a8ba; }
#projetos ul li.project > img, #projetos .momentum-preview { height:220px; width:100%; object-fit:cover; border-radius:8px; }
#projetos .project-description { margin:.65rem 0; text-align:left; opacity:.9; }
#projetos .project-tags { display:flex; flex-wrap:wrap; gap:.45rem; margin:.5rem 0 1rem; }
#projetos .project-tags span { font-size:.75rem; padding:.2rem .65rem; }
#projetos ul li.project > p:last-child { margin-top:auto; }
#projetos ul li a.git { border:1px solid #596583; border-radius:7px; text-align:center; }
#projetos ul li a.link { justify-content:flex-start; }
#projetos ul li a.link h3 { font-size:1.3rem; text-align:left; }
#projetos ul li a.link small { font-size:.75rem; font-weight:400; }
.contact-cta { display:flex; width:max-content; margin:0 auto 2rem; }
#contatos ul li { transition:transform .2s ease; }
#contatos ul li:hover { transform:translateY(-4px); }
footer { background:#181a2f; display:flex; justify-content:space-between; align-items:center; gap:1rem; padding:1.5rem clamp(1rem,6vw,5rem); font-size:.9rem; }
footer a { color:#e4e6ff; }
@media(max-width:768px) {
  header { justify-content:flex-end; }
  .menu-toggle { display:block; }
  header nav { display:none; position:absolute; top:100%; left:0; right:0; background:#181a2f; padding:1rem; box-shadow:0 12px 25px #0005; }
  header nav.menu-open { display:block; }
  header nav ul { flex-direction:column; align-items:center; gap:.9rem; }
  .skills-groups,.journey-grid,.grid-projetos { grid-template-columns:1fr; }
  #inicio .inicio-container { text-align:center; }
  .hero-actions { justify-content:center; }
  footer { flex-direction:column; text-align:center; }
}
@media(prefers-reduced-motion:reduce) {
  :global(html) { scroll-behavior:auto; }
  *,*::before,*::after { transition:none !important; animation:none !important; }
}

</style>