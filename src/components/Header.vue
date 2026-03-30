<template>
  <header class="main-header">
    <nav class="navbar">
      <a href="#about" class="logo" @click="navigate('#about')">🌸 Ikbel Bouzouita</a>

      <button
        class="menu-toggle"
        type="button"
        :aria-expanded="menuOpen ? 'true' : 'false'"
        aria-label="Toggle navigation menu"
        @click="menuOpen = !menuOpen"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>

      <ul class="nav-links" :class="{ open: menuOpen }">
        <li><a :class="{ active: currentSection === '#about' }" href="#about" @click.prevent="navigate('#about')">👤 About</a></li>
        <li><a :class="{ active: currentSection === '#skills' }" href="#skills" @click.prevent="navigate('#skills')">🧠 Skills</a></li>
        <li><a :class="{ active: currentSection === '#experience' }" href="#experience" @click.prevent="navigate('#experience')">💼 Experience</a></li>
        <li><a :class="{ active: currentSection === '#projects' }" href="#projects" @click.prevent="navigate('#projects')">📂 Projects</a></li>
        <li><a :class="{ active: currentSection === '#contact' }" href="#contact" @click.prevent="navigate('#contact')">📬 Contact</a></li>
      </ul>
    </nav>


  </header>
</template>

<script>
export default {
  name: 'Header',
  data() {
    return {
      menuOpen: false,
      currentSection: window.location.hash || '#about'
    };
  },
  computed: {
    sectionLabel() {
      const labels = {
        '#about': 'ABOUT',
        '#skills': 'SKILLS',
        '#experience': 'EXPERIENCE',
        '#projects': 'PROJECTS',
        '#contact': 'CONTACT'
      };
      return labels[this.currentSection] || 'HOME';
    }
  },
  methods: {
    closeMenu() {
      this.menuOpen = false;
    },
    updateSection() {
      this.currentSection = window.location.hash || '#about';
    },
    navigate(hash) {
      this.menuOpen = false;
      this.currentSection = hash;
      window.location.hash = hash;
      setTimeout(() => window.scrollTo({ top: document.querySelector(hash)?.offsetTop - 70 || 0, behavior: 'smooth' }), 50);
    }
  },
  mounted() {
    window.addEventListener('hashchange', this.updateSection);
    this.updateSection();
  },
  beforeUnmount() {
    window.removeEventListener('hashchange', this.updateSection);
  }
};
</script>

<style scoped>
.main-header {
  position: sticky;
  top: 0;
  z-index: 1000;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--line);
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
  padding-top: 0.25rem;
}

.navbar {
  max-width: 1200px;
  margin: 0 auto;
  min-height: 72px;
  padding: 0.6rem 1rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  position: relative;
}

.logo {
  color: var(--primary);
  text-decoration: none;
  font-weight: 700;
  letter-spacing: 0.3px;
  white-space: nowrap;
  font-size: 1.1rem;
}

.menu-toggle {
  display: none;
  width: 42px;
  height: 42px;
  border-radius: 10px;
  border: 1px solid var(--line);
  background: transparent;
  cursor: pointer;
  padding: 8px;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 5px;
}

.menu-toggle span {
  width: 18px;
  height: 2px;
  background: var(--text-primary);
  display: block;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 1.25rem;
  margin: 0;
  padding: 0;
}

.nav-links a {
  color: var(--text-secondary);
  text-decoration: none;
  font-size: 0.95rem;
  transition: all 0.25s ease;
  padding: 0.5rem 0.75rem;
  border-radius: 8px;
}

.nav-links a:hover,
.nav-links a.active {
  color: var(--primary);
  background: rgba(109, 40, 217, 0.08);
}

.nav-links a.active {
  background: rgba(109, 40, 217, 0.12);
  font-weight: 500;
}





@media (max-width: 900px) {
  .menu-toggle {
    display: inline-flex;
  }

  .nav-links {
    position: absolute;
    top: calc(100% + 8px);
    right: 1rem;
    left: 1rem;
    display: grid;
    gap: 0.35rem;
    background: var(--white);
    border: 1px solid var(--line);
    border-radius: 12px;
    padding: 0.6rem;
    box-shadow: 0 12px 30px rgba(0, 0, 0, 0.15);
    transform: translateY(-6px);
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.2s ease, transform 0.2s ease;
  }

  .nav-links.open {
    transform: translateY(0);
    opacity: 1;
    pointer-events: auto;
  }

  .nav-links a {
    display: block;
    width: 100%;
    padding: 0.7rem 0.75rem;
    border-radius: 8px;
  }

  .nav-links a:hover {
    background: rgba(109, 40, 217, 0.08);
  }
}
</style>