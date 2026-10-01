<script setup>
import { computed, ref } from 'vue'

const projects = [
  {
    number: '01 / 06',
    title: 'Movie Watcher',
    description: 'A Laravel project exploring a more personal alternative to IMDb, centered around users and their movie discovery experience.',
    type: 'Laravel / full-stack concept',
    image: '/projects/movie-watcher-logo.png',
    link: 'https://github.com/RensKooijman/The-movie-watcher',
  },
  {
    number: '02 / 06',
    title: 'Attendance System',
    description: 'A solo Laravel and Bootstrap project focused on CRUD operations, data management, and responsive attendance tracking.',
    type: 'Laravel / Bootstrap',
    image: '/projects/site2.png',
    link: 'https://github.com/RensKooijman/crud',
  },
  {
    number: '03 / 06',
    title: 'Dice',
    description: 'A digital dice application created to sharpen interface design, programming logic, and independent execution.',
    type: 'JavaScript / interface',
    image: '/projects/site3.png',
    link: 'https://rens-kooijman.com/public/index.php/dice',
  },
  {
    number: '04 / 06',
    title: 'Krashosting',
    description: 'A school team project built in 30 hours: explore and purchase hosting packages with a Spring Boot API behind the experience.',
    type: 'Spring Boot / team project',
    image: '/projects/site.png',
    link: 'https://krashosting-lite.tobiasvandeven.nl/home/',
  },
  {
    number: '05 / 06',
    title: 'Wordle API',
    description: 'A Laravel backend with accounts, words, leaderboards, API-token middleware, and request throttling for a Wordle-style game.',
    type: 'Laravel / REST API',
    image: '/projects/site1.png',
    link: 'https://github.com/RensKooijman/wordle-api',
  },
  {
    number: '06 / 06',
    title: "Valentine's Proposal",
    description: 'A playful, mobile-friendly interactive Valentine experience with animated styling and a cat-with-flower visual.',
    type: 'HTML / CSS / JavaScript',
    image: '/projects/valentine-catflower.gif',
    link: 'http://valentine.rens-kooijman.com/',
  },
]

const experiencePanels = [
  {
    id: 'events',
    label: 'Events',
    entries: [{ year: '2023', role: 'Hackathon', description: 'A friendly web development competition where students from different institutions collaborate under time pressure. Teams combine coding, design, problem-solving, and presentation skills to create a functional website for a judging panel.' }],
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
      { year: '2022 — now', role: 'Domino’s Pizza', description: 'As a bicycle courier, developing time management, customer service, punctuality, and multitasking skills while keeping service quality high.' },
      { year: '2021', role: 'McDonald’s', description: 'As a batch cook, learning teamwork, efficiency, consistency, and customer service in a fast-paced working environment.' },
    ],
  },
  {
    id: 'hobbies',
    label: 'Hobbies',
    entries: [
      { year: '2018 — now', role: 'Basketball', description: 'Playing and training, building teamwork, leadership, adaptability, communication, and the ability to motivate others.' },
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