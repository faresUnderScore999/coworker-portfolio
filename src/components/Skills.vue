<template>
  <section id="skills" class="skills">
    <h2>🧩 Skills</h2>
    <div class="skills-grid">
      <article class="skill-category">
        <div class="category-icon">💻</div>
        <h3>Programming Languages</h3>
        <ul class="skill-list">
          <li>Java</li>
          <li>Python</li>
          <li>JavaScript</li>
          <li>Langage C</li>
          <li>MATLAB</li>
        </ul>
      </article>
      <article class="skill-category">
        <div class="category-icon">🌐</div>
        <h3>Web Development</h3>
        <ul class="skill-list">
          <li>HTML/CSS</li>
          <li>Angular</li>
          <li>React.js</li>
          <li>Node.js</li>
          <li>Express.js</li>
          <li>Spring Boot</li>
          <li>Symfony</li>
        </ul>
      </article>
      <article class="skill-category">
        <div class="category-icon">☁️</div>
        <h3>Cloud & DevOps</h3>
        <ul class="skill-list">
          <li>Docker</li>
          <li>VMware</li>
          <li>Vagrant</li>
          <li>Packer</li>
          <li>MySQL</li>
          <li>MongoDB</li>
        </ul>
      </article>
      <article class="skill-category">
        <div class="category-icon">🛠️</div>
        <h3>Tools & Design</h3>
        <ul class="skill-list">
          <li>Eclipse</li>
          <li>Visual Studio</li>
          <li>Android Studio</li>
          <li>Postman</li>
          <li>StarUML</li>
          <li>Figma</li>
          <li>Photoshop</li>
          <li>Canva</li>
        </ul>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Skills'
}
</script>

<style scoped>
.skills {
  background: var(--white);
}

h2 {
  text-align: center;
  margin-top: 0;
  margin-bottom: 2rem;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.25rem;
}

.skill-category {
  border: 1px solid var(--line-light);
  border-radius: var(--radius-lg);
  padding: 1.5rem;
  transition: all var(--transition-base);
  background: var(--bg-1);
  position: relative;
  overflow: hidden;
}

.skill-category::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 4px;
  background: linear-gradient(90deg, var(--primary), var(--secondary));
  transform: scaleX(0);
  transform-origin: left;
  transition: transform var(--transition-base);
}

.skill-category:hover {
  transform: translateY(-6px);
  box-shadow: var(--shadow-lg);
  border-color: var(--primary-light);
}

.skill-category:hover::before {
  transform: scaleX(1);
}

.category-icon {
  font-size: 2rem;
  margin-bottom: 0.75rem;
}

h3 {
  margin: 0 0 1rem;
  color: var(--text-primary);
  font-size: 1.15rem;
  font-weight: 600;
}

.skill-list {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.skill-list li {
  color: var(--text-secondary);
  font-size: 0.9rem;
  padding: 0.35rem 0.75rem;
  background: var(--panel);
  border-radius: var(--radius-sm);
  border: 1px solid var(--line-light);
  transition: all var(--transition-fast);
}

.skill-list li:hover {
  background: var(--primary-50);
  color: var(--primary-dark);
  border-color: var(--primary-light);
}

@media (max-width: 768px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }
  
  .skill-category {
    padding: 1.25rem;
  }
}
</style>