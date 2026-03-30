<template>
  <section id="skills" class="skills">
    <h2>🧩 Skills</h2>
    <div class="skills-grid">
      <article class="skill-category">
        <h3>💻 Programming Languages</h3>
        <ul>
          <li>Java</li>
          <li>Python</li>
          <li>JavaScript</li>
          <li>Langage C</li>
          <li>MATLAB</li>
        </ul>
      </article>

      <article class="skill-category">
        <h3>🌐 Web Development</h3>
        <ul>
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
        <h3>☁️ Cloud & DevOps</h3>
        <ul>
          <li>Docker</li>
          <li>VMware</li>
          <li>Vagrant</li>
          <li>Packer</li>
          <li>MySQL</li>
          <li>MongoDB</li>
        </ul>
      </article>

      <article class="skill-category">
        <h3>🛠️ Tools & Design</h3>
        <ul>
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
  border-radius: 16px;
  padding: 2.2rem 1.4rem;
  box-shadow: var(--glow), 0 10px 30px rgba(0, 0, 0, 0.08);
}

h2 {
  text-align: center;
  margin-top: 0;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
  gap: 1rem;
}

.skill-category {
  border: 1px solid var(--line);
  border-radius: 12px;
  padding: 1rem;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
  background: var(--bg-1);
}

.skill-category:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 22px rgba(109, 40, 217, 0.1);
  border-color: var(--primary-light);
}

h3 {
  margin-top: 0;
  color: var(--primary);
  font-size: 1.1rem;
}

li {
  color: var(--text-secondary);
  margin-bottom: 0.25rem;
}

ul {
  margin: 0;
  padding-left: 1rem;
}

.state {
  margin: 0.2rem 0 0.6rem;
  color: var(--text-muted);
  font-size: 0.92rem;
}

.state.error {
  color: #ef4444;
}

.deep-skills {
  margin-top: 0.9rem;
  display: grid;
  gap: 0.7rem;
}

.deep-group h4 {
  margin: 0 0 0.35rem;
  color: var(--text-muted);
  font-size: 0.9rem;
}

.chips {
  display: flex;
  flex-wrap: wrap;
  gap: 0.45rem;
}

.chip {
  font-size: 0.78rem;
  border: 1px solid var(--line);
  border-radius: 999px;
  padding: 0.2rem 0.55rem;
  color: var(--text-secondary);
  background: rgba(109, 40, 217, 0.05);
}

.repo-note {
  margin-top: 0.8rem;
  color: var(--text-muted);
  font-size: 0.8rem;
}
</style>