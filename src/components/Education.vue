<template>
  <section id="education" class="education">
    <h2>🎓 Education</h2>
    <div class="timeline">
      <article class="timeline-item">
        <div class="timeline-marker"></div>
        <div class="timeline-content">
          <h3>🏫 Ecole Supérieure Privée d'Ingénierie et de Technologies (ESPRIT)</h3>
          <p class="period">2024 - Present</p>
          <ul>
            <li>Cycle ingénieur – Architecture IT & Cloud Computing</li>
            <li>Specialized in IT infrastructure, cloud computing, and DevOps</li>
            <li>Advanced coursework in virtualization, containerization, and cloud architecture</li>
          </ul>
        </div>
      </article>
      <article class="timeline-item">
        <div class="timeline-marker"></div>
        <div class="timeline-content">
          <h3>🏛️ Faculté des Sciences de Tunis (FST)</h3>
          <p class="period">2021 - 2024</p>
          <ul>
            <li>Licence en Génie Logiciel et Système d'Information</li>
            <li>Software engineering and information systems degree</li>
            <li>Focus on software development methodologies and system design</li>
          </ul>
        </div>
      </article>
      <article class="timeline-item">
        <div class="timeline-marker"></div>
        <div class="timeline-content">
          <h3>🎓 Lycée Ibn Khaldoun Tunisie</h3>
          <p class="period">2019 - 2020</p>
          <ul>
            <li>Baccalauréat mathématique</li>
            <li>Mathematics-focused high school diploma</li>
            <li>Strong foundation in mathematical concepts and problem-solving</li>
          </ul>
        </div>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Education'
}
</script>

<style scoped>
.education {
  background: linear-gradient(180deg, var(--white), var(--bg-1));
}

h2 {
  margin-top: 0;
  margin-bottom: 2rem;
  text-align: center;
}

.timeline {
  position: relative;
  padding-left: 2rem;
}

.timeline::before {
  content: '';
  position: absolute;
  left: 7px;
  top: 8px;
  bottom: 8px;
  width: 2px;
  background: linear-gradient(180deg, var(--secondary), var(--primary));
  border-radius: 2px;
}

.timeline-item {
  position: relative;
  padding-left: 2rem;
  padding-bottom: 1.75rem;
  transition: transform var(--transition-base);
}

.timeline-item:last-child {
  padding-bottom: 0;
}

.timeline-item:hover {
  transform: translateX(4px);
}

.timeline-marker {
  position: absolute;
  left: -2rem;
  top: 6px;
  width: 16px;
  height: 16px;
  background: var(--white);
  border: 3px solid var(--secondary);
  border-radius: 50%;
  z-index: 1;
  transition: all var(--transition-base);
}

.timeline-item:hover .timeline-marker {
  background: var(--secondary);
  box-shadow: 0 0 0 4px rgba(13, 148, 136, 0.2);
}

.timeline-content {
  background: var(--white);
  border: 1px solid var(--line-light);
  border-radius: var(--radius-lg);
  padding: 1.25rem;
  transition: all var(--transition-base);
}

.timeline-item:hover .timeline-content {
  box-shadow: var(--shadow-md);
  border-color: var(--secondary-light);
}

h3 {
  margin: 0 0 0.4rem;
  color: var(--text-primary);
  font-size: 1.1rem;
  font-weight: 600;
}

.period {
  margin: 0 0 0.75rem;
  color: var(--primary);
  font-size: 0.9rem;
  font-weight: 500;
}

ul {
  margin: 0;
  padding-left: 1.1rem;
}

li {
  color: var(--text-secondary);
  margin-bottom: 0.35rem;
  line-height: 1.5;
}

li:last-child {
  margin-bottom: 0;
}

@media (max-width: 768px) {
  .timeline {
    padding-left: 1.5rem;
  }
  
  .timeline::before {
    left: 5px;
  }
  
  .timeline-item {
    padding-left: 1.5rem;
  }
  
  .timeline-marker {
    left: -1.5rem;
    width: 12px;
    height: 12px;
  }
  
  .timeline-content {
    padding: 1rem;
  }
  
  h3 {
    font-size: 1rem;
  }
}
</style>