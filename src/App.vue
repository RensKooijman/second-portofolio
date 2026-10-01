<script setup>
import { computed, ref } from 'vue'

const projects = [
  {
    number: '01 / 07',
    title: 'Movie Watcher',
    description: 'A Laravel project exploring a more personal alternative to IMDb, centered around users and their movie discovery experience.',
    type: 'Personal media platform / full-stack concept / solo project',
    image: '/projects/movie-watcher-logo.png',
    link: 'https://github.com/RensKooijman/The-movie-watcher',
    badges: [
      { label: 'PHP', src: 'https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white' },
      { label: 'Laravel', src: 'https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white' },
      { label: 'Blade', src: 'https://img.shields.io/badge/Blade-FF2D20?style=flat-square&logo=laravel&logoColor=white' },
    ],
  },
  {
    number: '02 / 07',
    title: "Valentine's Proposal",
    description: 'A playful, mobile-friendly interactive Valentine experience with animated styling and a cat-with-flower visual.',
    type: 'Interactive experience / solo project',
    image: '/projects/valentine-catflower.gif',
    link: 'http://valentine.rens-kooijman.com/',
    badges: [
      { label: 'HTML5', src: 'https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white' },
      { label: 'CSS3', src: 'https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white' },
      { label: 'JavaScript', src: 'https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=111111' },
    ],
  },
  {
    number: '03 / 07',
    title: 'Attendance System',
    description: 'A solo Laravel and Bootstrap project focused on CRUD operations, data management, and responsive attendance tracking.',
    type: 'Attendance web application / solo project',
    image: '/projects/site2.png',
    link: 'https://github.com/RensKooijman/crud',
    badges: [
      { label: 'PHP', src: 'https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white' },
      { label: 'Laravel', src: 'https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white' },
      { label: 'Bootstrap', src: 'https://img.shields.io/badge/Bootstrap-7952B3?style=flat-square&logo=bootstrap&logoColor=white' },
    ],
  },
  {
    number: '04 / 07',
    title: 'Spaceships',
    description: 'A working PHP web project built around reusable Spaceship objects and a simple browser-facing entry point.',
    type: 'Object-oriented web project / team project',
    image: '/projects/spaceships.png',
    link: 'https://github.com/RensKooijman/Spaceships',
    badges: [
      { label: 'PHP', src: 'https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white' },
    ],
  },
  {
    number: '05 / 07',
    title: 'Dice',
    description: 'A digital dice application created to sharpen interface design, programming logic, and independent execution.',
    type: 'Browser game / solo project',
    image: '/projects/site3.png',
    link: 'https://rens-kooijman.com/public/index.php/dice',
    badges: [
      { label: 'HTML5', src: 'https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white' },
      { label: 'CSS3', src: 'https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white' },
      { label: 'JavaScript', src: 'https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=111111' },
    ],
  },
  {
    number: '06 / 07',
    title: 'Krashosting',
    description: 'A school team project built in 30 hours: explore and purchase hosting packages with a Spring Boot API behind the experience.',
    type: 'Hosting platform / team project',
    image: '/projects/site.png',
    link: 'https://krashosting-lite.tobiasvandeven.nl/home/',
    badges: [
      { label: 'Java', src: 'https://img.shields.io/badge/Java-ED8B00?style=flat-square&logo=openjdk&logoColor=white' },
      { label: 'Spring Boot', src: 'https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white' },
      { label: 'HTML5', src: 'https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white' },
    ],
  },
  {
    number: '07 / 07',
    title: 'Wordle API',
    description: 'A Laravel backend with accounts, words, leaderboards, API-token middleware, and request throttling for a Wordle-style game.',
    type: 'Game backend / team project',
    image: '/projects/site1.png',
    link: 'https://github.com/RensKooijman/wordle-api',
    badges: [
      { label: 'PHP', src: 'https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white' },
      { label: 'Laravel', src: 'https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white' },
      { label: 'REST API', src: 'https://img.shields.io/badge/REST_API-02569B?style=flat-square&logo=fastapi&logoColor=white' },
    ],
  },
]

const experiencePanels = [
  {
    id: 'events',
    label: 'Events',
    entries: [
      { year: '2025', role: 'School expo', description: 'A friendly web development competition where students from the same institutions participate to showcase their project with the same goals for a judging panel. i became second of this competition.' },
      { year: '2023', role: 'Hackathon', description: 'A friendly web development competition where students from different institutions collaborate under time pressure. Teams combine coding, design, problem-solving, and presentation skills to create a functional website for a judging panel.' },
    ],
  },
  {
    id: 'education',
    label: 'Education',
    entries: [
      { year: '2025 — now', role: 'AVANS Breda', description: 'Applied Computer Science, studying programming, software development, databases, problem-solving, and teamwork through practical projects.' },
      { year: '2021 — 2025', role: 'ROC Tilburg', description: 'Webdevelopment across front-end and back-end development, with a particular interest in designing the reliable systems behind an application.' },
      { year: '2017 — 2021', role: 'Curio Effent', description: 'VMBO-GT, where mathematics, physics, chemistry, and economics strengthened an analytical approach to solving problems.' },
      { year: '2009 — 2017', role: 'OBS Pionier', description: 'The first spark of interest in games, logical reasoning, and the possibilities of coding that eventually led toward web development.' },
    ],
  },
  {
    id: 'work',
    label: 'Work',
    entries: [
      { year: '2025 — now', role: 'Solvware', description: 'Working on various projects for different clients, gaining experience in different industries and technologies.' },
      { year: '2024 — 2025', role: 'Internship(Solvware)', description: 'Gaining hands-on experience in a real-world setting, applying theoretical knowledge to practical situations, and developing professional skills.' },
      { year: '2022 — 2024', role: 'Domino’s Pizza', description: 'As a bicycle courier, developing time management, customer service, punctuality, and multitasking skills while keeping service quality high.' },
      { year: '2021 — 2021', role: 'McDonald’s', description: 'As a batch cook, learning teamwork, efficiency, consistency, and customer service in a fast-paced working environment.' },
    ],
  },
  {
    id: 'hobbies',
    label: 'Hobbies',
    entries: [
      { year: '2012 — now', role: 'Gaming', description: 'Exploring various genres, developing strategic thinking, and improving hand-eye coordination through immersive experiences.' },
      { year: '2026 — now', role: 'Gym', description: 'Regular exercise and training to maintain physical fitness and overall well-being.' },
      { year: '2018 — 2026', role: 'Basketball', description: 'Playing and training, building teamwork, leadership, adaptability, communication, and the ability to motivate others.' },
      { year: '2014 — 2022', role: 'Tennis', description: 'A mix of fitness, resilience, strategy, quick thinking, and adapting to opponents through both solo and doubles play.' },
      { year: '2018 — 2021', role: 'Chess', description: 'Developing strategic thinking, analytical problem-solving, patience, and decision-making under pressure.' },
      { year: '2012 — 2018', role: 'Soccer', description: 'Learning collaboration through passing, creating opportunities for teammates, and understanding collective success.' },
    ],
  },
]

const skills = Array.from({ length: 12 }, (_, index) => `/projects/image${index + 1}.png`)
const activePanel = ref('events')
const currentProjectPage = ref(1)
const projectsPerPage = 5
const projectPageCount = computed(() => Math.ceil(projects.length / projectsPerPage))
const paginatedProjects = computed(() => {
  const start = (currentProjectPage.value - 1) * projectsPerPage
  return projects.slice(start, start + projectsPerPage)
})

function setProjectPage(page) {
  currentProjectPage.value = page
}
</script>

<template>
  <main class="portfolio">
    <nav class="nav" aria-label="Main navigation">
      <a class="wordmark" href="#top">RENS<br />KOOIJMAN<span>.</span></a>
      <div class="nav-links">
        <a href="#work">Projects</a>
        <a href="#experience">Experience</a>
        <a href="#contact">Contact <span aria-hidden="true">↗</span></a>
      </div>
    </nav>

    <section id="top" class="hero" aria-labelledby="hero-title">
      <div class="portrait-wrap">
        <div class="skill-orbit" aria-hidden="true">
          <span v-for="(skill, index) in skills" :key="skill" class="skill-node" :style="{ '--i': index }">
            <img :src="skill" alt="" />
          </span>
        </div>
        <div class="portrait" role="img" aria-label="Rens Kooijman portrait">
          <span>RK</span>
          <img src="/profile.jpg" alt="Rens Kooijman" @error="$event.currentTarget.hidden = true" />
        </div>
        <span class="portrait-caption">That’s me<br />in a circle.</span>
      </div>
      <p class="eyebrow">Designer / developer / human</p>
      <h1 id="hero-title">Hi, I’m Rens.<br />I make the<br /><em>web</em> work.</h1>
      <div class="hero-footer">
        <p class="intro">I’m a web developer who enjoys turning ideas into working experiences, learning new technology, and solving the tricky bit in the middle.</p>
        <a class="scroll-link" href="#work">See the work <span aria-hidden="true">↓</span></a>
      </div>
    </section>

    <section id="work" class="work section-rule" aria-labelledby="work-title">
      <div class="section-heading">
        <p class="eyebrow">01 / Projects</p>
        <h2 id="work-title">Things I’ve<br /><em>made</em></h2>
      </div>
      <div class="project-list">
        <article v-for="project in paginatedProjects" :key="project.number" class="project">
          <div class="project-media">
            <img :src="project.image" :alt="`${project.title} project preview`" />
            <span class="project-index">{{ project.number }}</span>
          </div>
          <div class="project-body">
            <p class="project-type">{{ project.type }}</p>
            <h3>{{ project.title }}</h3>
            <p>{{ project.description }}</p>
            <div class="project-badges" aria-label="Technologies used">
              <img v-for="badge in project.badges" :key="badge.label" :src="badge.src" :alt="badge.label" loading="lazy" />
            </div>
            <a :href="project.link" target="_blank" rel="noreferrer" class="project-link">Visit project <span aria-hidden="true">↗</span></a>
          </div>
        </article>
      </div>
      <nav v-if="projectPageCount > 1" class="project-pagination" aria-label="Project pages">
        <button type="button" aria-label="Previous projects" :disabled="currentProjectPage === 1" @click="setProjectPage(currentProjectPage - 1)">←</button>
        <button v-for="page in projectPageCount" :key="page" type="button" :class="{ 'is-current': currentProjectPage === page }" :aria-current="currentProjectPage === page ? 'page' : undefined" :aria-label="`Project page ${page}`" @click="setProjectPage(page)">{{ page }}</button>
        <button type="button" aria-label="Next projects" :disabled="currentProjectPage === projectPageCount" @click="setProjectPage(currentProjectPage + 1)">→</button>
      </nav>
    </section>

    <section id="experience" class="experience section-rule" aria-labelledby="experience-title">
      <div class="section-heading">
        <p class="eyebrow">02 / Experience</p>
        <h2 id="experience-title">A few places<br />I’ve <em>been</em>.</h2>
      </div>
      <div class="life-accordion" role="tablist" aria-label="Experience categories">
        <article v-for="(panel, index) in experiencePanels" :key="panel.id" class="life-panel" :class="{ 'is-open': activePanel === panel.id }">
          <button class="life-tab" type="button" role="tab" :aria-selected="activePanel === panel.id" :aria-controls="`${panel.id}-content`" @click="activePanel = panel.id">
            <span class="life-tab-number">0{{ index + 1 }}</span>
            <span>{{ panel.label }}</span>
            <span class="life-tab-arrow" aria-hidden="true">↗</span>
          </button>
          <Transition name="accordion" mode="out-in">
            <div v-if="activePanel === panel.id" :id="`${panel.id}-content`" class="life-content" role="tabpanel">
              <article v-for="entry in panel.entries" :key="`${panel.id}-${entry.role}`" class="life-entry">
                <span class="life-year">{{ entry.year }}</span>
                <h3>{{ entry.role }}</h3>
                <p>{{ entry.description }}</p>
              </article>
            </div>
          </Transition>
        </article>
      </div>
    </section>

    <section id="contact" class="contact section-rule" aria-labelledby="contact-title">
      <p class="eyebrow">03 / Contact</p>
      <h2 id="contact-title">Have a good<br /><em>idea?</em> Say hello.</h2>
      <a class="outline-link" href="mailto:webmaster@rens-koijman.com">webmaster@rens-koijman.com <span aria-hidden="true">↗</span></a>
      <div class="social-links">
        <a href="https://www.linkedin.com/in/rens-kooijman-1130a9189/" target="_blank" rel="noreferrer">LinkedIn ↗</a>
        <a href="https://github.com/RensKooijman" target="_blank" rel="noreferrer">GitHub ↗</a>
      </div>
    </section>

    <footer class="footer section-rule">
      <span>© 2025 Rens Kooijman</span>
      <span>Made with curiosity + Vue</span>
      <a href="#top">Back to top ↑</a>
    </footer>
  </main>
</template>