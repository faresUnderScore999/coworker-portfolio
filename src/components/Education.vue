<template>
  <section id="education" class="education">
    <h2>🎓 Education</h2>

    <article class="timeline-item">
      <h3>🏫 Ecole Supérieure Privée d'Ingénierie et de Technologies (ESPRIT)</h3>
      <p class="period">2024 - Present</p>
      <ul>
        <li>Cycle ingénieur – Architecture IT & Cloud Computing</li>
        <li>Specialized in IT infrastructure, cloud computing, and DevOps</li>
        <li>Advanced coursework in virtualization, containerization, and cloud architecture</li>
      </ul>
    </article>

    <article class="timeline-item">
      <h3>🏛️ Faculté des Sciences de Tunis (FST)</h3>
      <p class="period">2021 - 2024</p>
      <ul>
        <li>Licence en Génie Logiciel et Système d'Information</li>
        <li>Software engineering and information systems degree</li>
        <li>Focus on software development methodologies and system design</li>
      </ul>
    </article>

    <article class="timeline-item">
      <h3>🎓 Lycée Ibn Khaldoun Tunisie</h3>
      <p class="period">2019 - 2020</p>
      <ul>
        <li>Baccalauréat mathématique</li>
        <li>Mathematics-focused high school diploma</li>
        <li>Strong foundation in mathematical concepts and problem-solving</li>
      </ul>
    </article>
  </section>
</template>

<script>
export default {
  name: 'Education'
}
</script>

<style scoped>
.education {
  background: color-mix(in srgb, var(--panel) 90%, transparent);
  border-radius: 16px;
  padding: 2.2rem 1.4rem;
  box-shadow: var(--glow), 0 10px 30px rgba(0, 0, 0, 0.35);
}

h2 {
  margin-top: 0;
  text-align: center;
}

.timeline-item {
  border: 1px solid color-mix(in srgb, var(--old-rose) 20%, var(--pastel-pink));
  border-radius: 12px;
  padding: 1rem;
  margin-bottom: 1rem;
  transition: transform 0.25s ease, box-shadow 0.25s ease;
}

.timeline-item:last-child {
  margin-bottom: 0;
}

.timeline-item:hover {
  transform: translateY(-4px);
  box-shadow: 0 10px 20px rgba(192, 132, 151, 0.16);
  border-color: var(--old-rose);
}

h3 {
  margin: 0 0 0.3rem;
  color: var(--old-rose);
}

.period {
  margin: 0 0 0.8rem;
  color: var(--text-soft);
  font-size: 0.95rem;
}

li {
  color: var(--text-soft);
}

ul {
  margin: 0;
  padding-left: 1.1rem;
}
</style>