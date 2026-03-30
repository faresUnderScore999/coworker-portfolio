<template>
  <header class="main-header">
    <nav class="navbar">
      <a href="#about" class="logo" @click="navigate('#about')">
        <span class="logo-icon">🌸</span> Ikbel Bouzouita
      </a>
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
        <li><a :class="{ active: currentSection === '#education' }" href="#education" @click.prevent="navigate('#education')">🎓 Education</a></li>
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
        '#education': 'EDUCATION',
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
  background: rgba(255, 255, 255, 0.92);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid var(--line-light);
  box-shadow: var(--shadow-sm);
}

.navbar {
  max-width: 1200px;
  margin: 0 auto;
  min-height: 72px;
  padding: 0.6rem 1.5rem;
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
  font-size: 1.15rem;
  display: flex;
  align-items: center;
  gap: 0.4rem;
  transition: transform var(--transition-base);
}

.logo:hover {
  transform: scale(1.02);
  text-decoration: none;
}

.logo-icon {
  font-size: 1.3rem;
}

.menu-toggle {
  display: none;
  width: 44px;
  height: 44px;
  border-radius: var(--radius-md);
  border: 1px solid var(--line);
  background: var(--white);
  cursor: pointer;
  padding: 10px;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 5px;
  transition: all var(--transition-base);
}

.menu-toggle:hover {
  background: var(--primary-50);
  border-color: var(--primary-light);
}

.menu-toggle span {
  width: 20px;
  height: 2px;
  background: var(--text-primary);
  display: block;
  border-radius: 2px;
  transition: all var(--transition-base);
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 0.5rem;
  margin: 0;
  padding: 0;
}

.nav-links a {
  color: var(--text-secondary);
  text-decoration: none;
  font-size: 0.95rem;
  font-weight: 500;
  transition: all var(--transition-base);
  padding: 0.6rem 0.9rem;
  border-radius: var(--radius-md);
  display: block;
}

.nav-links a:hover,
.nav-links a.active {
  color: var(--primary);
  background: var(--primary-50);
}

.nav-links a.active {
  background: var(--primary-100);
  font-weight: 600;
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
    border-radius: var(--radius-lg);
    padding: 0.75rem;
    box-shadow: var(--shadow-lg);
    transform: translateY(-10px);
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.25s ease, transform 0.25s ease;
  }

  .nav-links.open {
    transform: translateY(0);
    opacity: 1;
    pointer-events: auto;
  }

  .nav-links a {
    display: block;
    width: 100%;
    padding: 0.8rem 1rem;
    border-radius: var(--radius-md);
  }

  .nav-links a:hover {
    background: var(--primary-50);
  }
}
</style>