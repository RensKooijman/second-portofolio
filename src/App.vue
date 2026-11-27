<script setup>
import { computed, ref } from 'vue'

const projects = [
  {
    number: '01 / 09',
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
    number: '02 / 09',
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
    number: '03 / 09',
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
    number: '04 / 09',
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
    number: '05 / 09',
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
    number: '06 / 09',
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
    number: '07 / 09',
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
  {
    number: '08 / 09',
    title: 'Eigen Site',
    description: 'My personal website and first portfolio, built with Laravel and Blade and styled with SCSS.',
    type: 'Personal portfolio / solo project',
    image: '/projects/eigen-site.svg',
    link: 'https://www.rens-kooijman.com/',
    badges: [
      { label: 'PHP', src: 'https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white' },
      { label: 'Laravel', src: 'https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white' },
      { label: 'Blade', src: 'https://img.shields.io/badge/Blade-FF2D20?style=flat-square&logo=laravel&logoColor=white' },
      { label: 'SCSS', src: 'https://img.shields.io/badge/SCSS-CC6699?style=flat-square&logo=sass&logoColor=white' },
    ],
  },
  {
    number: '09 / 09',
    title: 'Second Portfolio',
    description: 'This portfolio, rebuilt with Vue 3 and Vite to present my projects, experience, and the technologies I work with.',
    type: 'Personal portfolio / solo project',
    image: '/projects/second-portfolio.svg',
    link: 'https://github.com/RensKooijman/second-portofolio',
    badges: [
      { label: 'Vue.js', src: 'https://img.shields.io/badge/Vue.js-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white' },
      { label: 'Vite', src: 'https://img.shields.io/badge/Vite-646CFF?style=flat-square&logo=vite&logoColor=white' },
      { label: 'JavaScript', src: 'https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=111111' },
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

const skillCategories = [
  { id: 'languages', name: 'Programming Languages', orbitLabel: 'Languages', skills: ['PHP', 'JavaScript', 'C#', 'Java', 'HTML', 'CSS', 'SQL'] },
  { id: 'frontend', name: 'Frontend Development', orbitLabel: 'Frontend', skills: ['SCSS', 'Bootstrap', 'Tailwind CSS', 'Alpine.js', 'jQuery', 'Chart.js', 'Vue.js'] },
  { id: 'backend', name: 'Backend Frameworks', orbitLabel: 'Backend', skills: ['Laravel', 'CodeIgniter', 'Livewire', 'Node.js', 'Blazor', 'NestJS', 'FastAPI'] },
  { id: 'databases', name: 'Databases', orbitLabel: 'Databases', skills: ['MySQL', 'Microsoft SQL Server', 'MongoDB', 'phpMyAdmin'] },
  { id: 'ai-ml', name: 'AI & Machine Learning', orbitLabel: 'AI / ML', skills: ['ChatGPT', 'Claude', 'Google Gemini', 'GitHub Copilot', 'Ollama', 'YOLO', 'Roboflow', 'Kaggle', 'NumPy', 'Pandas'] },
  { id: 'packages', name: 'Package Managers', orbitLabel: 'Packages', skills: ['Composer', 'NPM', 'PyPI'] },
  { id: 'apis-tools', name: 'APIs & Development Tools', orbitLabel: 'API Tools', skills: ['Postman', 'Swagger', 'JSON', 'LanguageTool API', 'ngrok'] },
  { id: 'cloud-devops', name: 'Cloud & DevOps', orbitLabel: 'Cloud', skills: ['Docker', 'Azure', 'Hostinger'] },
  { id: 'version-control', name: 'Version Control', orbitLabel: 'Version', skills: ['Git', 'Bitbucket', 'GitHub Copilot'] },
  { id: 'environment', name: 'Development Environment', orbitLabel: 'Environment', skills: ['XAMPP', 'MAMP', 'Windows Terminal', 'PowerShell', 'FileZilla'] },
  { id: 'design', name: 'Design & Productivity', orbitLabel: 'Design', skills: ['Figma', 'Adobe', 'Jira', 'Trello'] },
  { id: 'games', name: 'Game Development', orbitLabel: 'Games', skills: ['Unity'] },
  { id: 'hardware-iot', name: 'Hardware & IoT', orbitLabel: 'Hardware', skills: ['Raspberry Pi', 'Arduino', 'NFC', 'MQTT'] },
  { id: 'cms', name: 'CMS & Platforms', orbitLabel: 'CMS', skills: ['Joomla'] },
]

const activeSkillCategory = ref(skillCategories[0].id)
const selectedSkillCategory = computed(() => skillCategories.find((category) => category.id === activeSkillCategory.value) ?? skillCategories[0])
const isSkillCategoryZoomed = ref(false)
const failedSkillIcons = ref(new Set())
const activePanel = ref('events')
const currentProjectPage = ref(1)
const projectsPerPage = 5
const skillIconOverrides = {
  PHP: 'https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/php.svg',
  JavaScript: 'https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/javascript.svg',
  'C#': 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/csharp/csharp-plain.svg',
  Java: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original.svg',
  'Vue.js': 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original.svg',
  HTML: 'https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/html5.svg',
  CSS: 'https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/css.svg',
  SQL: 'https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/postgresql.svg',
  'Microsoft SQL Server': 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/microsoftsqlserver/microsoftsqlserver-original.svg',
  Joomla: 'https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/joomla.svg',
  ChatGPT: 'https://raw.githubusercontent.com/lobehub/lobe-icons/master/packages/static-svg/icons/openai.svg',
  Azure: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/azure/azure-original.svg',
  PowerShell: 'https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/powershell/powershell-original.svg',
  Adobe: 'https://cdn.jsdelivr.net/npm/@lobehub/icons-static-svg@latest/icons/adobe.svg',
}
const projectPageCount = computed(() => Math.ceil(projects.length / projectsPerPage))
const paginatedProjects = computed(() => {
  const start = (currentProjectPage.value - 1) * projectsPerPage
  return projects.slice(start, start + projectsPerPage)
})

function setProjectPage(page) {
  currentProjectPage.value = page
}

function selectSkillCategory(categoryId) {
  activeSkillCategory.value = categoryId
  isSkillCategoryZoomed.value = true
}

function backToSkillCategories() {
  isSkillCategoryZoomed.value = false
}

function radialStyle(index, total) {
  const angle = (360 * index) / total
  return {
    '--angle': `${angle}deg`,
    '--counter-angle': `${-angle}deg`,
    '--delay': `${index * 55}ms`,
  }
}

function skillIconUrl(skill) {
  if (skillIconOverrides[skill]) return skillIconOverrides[skill]

  const aliases = {
    SCSS: 'sass',
    'Tailwind CSS': 'tailwindcss',
    'Alpine.js': 'alpinedotjs',
    'Chart.js': 'chartdotjs',
    'Node.js': 'nodedotjs',
    'Google Gemini': 'googlegemini',
    YOLO: 'ultralytics',
    'LanguageTool API': 'languagetool',
    'Windows Terminal': 'windowsterminal',
    'Raspberry Pi': 'raspberrypi',
    'GitHub Copilot': 'githubcopilot',
  }
  const slug = aliases[skill] ?? skill.toLowerCase().replace(/[^a-z0-9]/g, '')
  return `https://raw.githubusercontent.com/simple-icons/simple-icons/develop/icons/${slug}.svg`
}

function skillInitials(skill) {
  return skill.split(/[\s.]+/).filter(Boolean).map((part) => part[0]).slice(0, 2).join('').toUpperCase()
}

function markSkillIconFailed(skill) {
  failedSkillIcons.value.add(skill)
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
        <Transition name="web-zoom" mode="out-in">
          <div
            v-if="!isSkillCategoryZoomed"
            id="skill-categories"
            key="categories"
            class="category-orbit"
            role="group"
            aria-label="Tech stack categories"
          >
            <button
              v-for="(category, index) in skillCategories"
              :key="category.id"
              class="category-node"
              :class="{ 'is-active': activeSkillCategory === category.id }"
              :style="radialStyle(index, skillCategories.length)"
              type="button"
              :aria-label="`Show ${category.name} technologies`"
              :aria-pressed="activeSkillCategory === category.id"
              :data-label="category.name"
              @click="selectSkillCategory(category.id)"
            >
              <img
                v-if="!failedSkillIcons.has(category.skills[0])"
                :src="skillIconUrl(category.skills[0])"
                alt=""
                loading="lazy"
                @error="markSkillIconFailed(category.skills[0])"
              />
              <span v-else class="category-node-fallback" aria-hidden="true">{{ skillInitials(category.skills[0]) }}</span>
              <span class="category-node-label">{{ category.orbitLabel }}</span>
            </button>
          </div>
          <div
            v-else
            :key="selectedSkillCategory.id"
            class="tech-orbit"
            role="group"
            :aria-label="`${selectedSkillCategory.name} technologies`"
          >
            <div class="tech-orbit-heading">
              <span class="tech-category-label">{{ selectedSkillCategory.name }}</span>
            </div>
            <div
              v-for="(skill, index) in selectedSkillCategory.skills"
              :key="skill"
              class="tech-node"
              :style="radialStyle(index, selectedSkillCategory.skills.length)"
              role="img"
              tabindex="0"
              :aria-label="`${skill} logo`"
              :data-label="skill"
            >
              <img
                v-if="!failedSkillIcons.has(skill)"
                :src="skillIconUrl(skill)"
                alt=""
                loading="lazy"
                @error="markSkillIconFailed(skill)"
              />
              <span v-else class="tech-node-fallback" aria-hidden="true">{{ skillInitials(skill) }}</span>
            </div>
          </div>
        </Transition>
        <Transition name="center-change" mode="out-in">
          <div v-if="!isSkillCategoryZoomed" key="portrait" class="portrait" role="img" aria-label="Rens Kooijman portrait">
            <span>RK</span>
            <img src="/profile.jpg" alt="Rens Kooijman" @error="$event.currentTarget.hidden = true" />
          </div>
          <button v-else key="back" class="portrait-back-button" type="button" aria-label="Back to tech stack categories" @click="backToSkillCategories">
            <span class="portrait-back-arrow" aria-hidden="true">←</span>
            <span class="portrait-back-label">Back</span>
          </button>
        </Transition>
        <span v-if="!isSkillCategoryZoomed" class="portrait-caption">That’s me<br />in a circle.</span>
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