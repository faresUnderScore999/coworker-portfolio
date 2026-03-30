<template>
  <div id="app">
    <Header />
    <main v-if="!selectedProject">
      <About />
      <Education />
      <Skills />
      <Experience />
      <Projects :projects="projects" @open-project="openProject" />
      <Contact />
    </main>
    <main v-else class="details-view">
      <ProjectDetails :project="selectedProject" @back="goHome" />
    </main>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import About from './components/About.vue';
import Education from './components/Education.vue';
import Skills from './components/Skills.vue';
import Experience from './components/Experience.vue';
import Projects from './components/Projects.vue';
import ProjectDetails from './components/ProjectDetails.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    About,
    Education,
    Skills,
    Experience,
    Projects,
    ProjectDetails,
    Contact,
    Footer
  },
  data() {
    return {
      observer: null,
      projects: [],
      selectedProject: null
    };
  },
  async mounted() {
    await Promise.all([this.loadProjects()]);
    window.addEventListener('hashchange', this.handleHashRoute);
    this.handleHashRoute();
    if (!this.selectedProject) {
      this.$nextTick(() => this.setupSectionObserver());
    }
  },
  beforeUnmount() {
    window.removeEventListener('hashchange', this.handleHashRoute);
    if (this.observer) {
      this.observer.disconnect();
    }
  },
  methods: {
    async loadProjects() {
      try {
        const response = await fetch('/data.json');
        if (!response.ok) throw new Error('Failed to load data.json');
        this.projects = await response.json();
      } catch (error) {
        console.error(error);
        this.projects = [];
      }
    },
    setupSectionObserver() {
      if (this.observer) {
        this.observer.disconnect();
      }
      this.observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              entry.target.classList.add('is-visible');
              this.observer.unobserve(entry.target);
            }
          });
        },
        { threshold: 0.1, rootMargin: '0px 0px -50px 0px' }
      );
      document.querySelectorAll('section').forEach((section) => {
        this.observer.observe(section);
      });
    },
    handleHashRoute() {
      const match = window.location.hash.match(/^#project\/(\d+)$/);
      if (match) {
        const index = Number(match[1]);
        this.selectedProject = this.projects[index] || null;
        window.scrollTo({ top: 0, behavior: 'smooth' });
      } else {
        this.selectedProject = null;
        this.$nextTick(() => this.setupSectionObserver());
      }
    },
    openProject(index) {
      this.selectedProject = this.projects[index] || null;
      window.location.hash = `project/${index}`;
      window.scrollTo({ top: 0, behavior: 'smooth' });
    },
    goHome() {
      this.selectedProject = null;
      const cleanUrl = `${window.location.pathname}${window.location.search}`;
      window.history.pushState(null, '', cleanUrl);
      this.$nextTick(() => {
        this.setupSectionObserver();
        const projectsSection = document.getElementById('projects');
        projectsSection?.scrollIntoView({ behavior: 'smooth', block: 'start' });
      });
    }
  }
};
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  background: transparent;
}

main {
  flex: 1;
  width: min(1200px, calc(100% - 2rem));
  margin: 1.25rem auto 0;
  padding-top: 1.5rem;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

section {
  scroll-margin-top: 88px;
  padding: 48px 32px;
  margin: 0;
  max-width: 100%;
  border-radius: var(--radius-lg);
  background: var(--white);
  border: 1px solid var(--line-light);
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.6s ease, transform 0.6s ease, box-shadow 0.3s ease, border-color 0.3s ease;
}

section:hover {
  box-shadow: var(--shadow-md);
}

.details-view {
  align-items: stretch;
}

section.is-visible {
  opacity: 1;
  transform: translateY(0);
}

@media (max-width: 768px) {
  main {
    width: calc(100% - 1rem);
    margin-top: 0.75rem;
    gap: 1rem;
  }
  
  section {
    padding: 28px 20px;
  }
}
</style>