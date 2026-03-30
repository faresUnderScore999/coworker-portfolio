<template>
  <section id="experience" class="experience">
    <h2>💼 Experience</h2>
    <div class="timeline">
      <article class="timeline-item">
        <div class="timeline-marker"></div>
        <div class="timeline-content">
          <h3>🚀 Application Web – Gestion des employés (Stage)</h3>
          <p class="period">2024 — Billcom</p>
          <ul>
            <li>Développement d'une application web pour la gestion des employés dans l'entreprise Billcom</li>
            <li>Technologies utilisées: Spring Boot, Angular, MySQL</li>
            <li>Conception et implémentation de fonctionnalités complètes de gestion RH</li>
          </ul>
        </div>
      </article>
      <article class="timeline-item">
        <div class="timeline-marker"></div>
        <div class="timeline-content">
          <h3>🎓 Plateforme Cloud – Gestion des abonnements de services Cloud (Projet de fin d'étude)</h3>
          <p class="period">2024 — ESPRIT</p>
          <ul>
            <li>Développement d'une application web permettant la gestion des abonnements et des services cloud</li>
            <li>Technologies: Node.js, Express.js, React.js, MongoDB</li>
            <li>Architecture cloud moderne avec gestion des utilisateurs et des services</li>
          </ul>
        </div>
      </article>
      <article class="timeline-item">
        <div class="timeline-marker"></div>
        <div class="timeline-content">
          <h3>💻 Application Desktop – Gestion des employés d'un laboratoire d'analyse</h3>
          <p class="period">2023 — Projet Académique</p>
          <ul>
            <li>Conception d'une application desktop permettant la gestion des employés et des données d'un laboratoire</li>
            <li>Technologies: Java, Java Swing, Eclipse, SQL Server</li>
            <li>Interface utilisateur intuitive avec gestion complète des données</li>
          </ul>
        </div>
      </article>
      <article class="timeline-item">
        <div class="timeline-marker"></div>
        <div class="timeline-content">
          <h3>🏢 Application Desktop – Gestion des employés dans une faculté</h3>
          <p class="period">2023 — Projet Académique</p>
          <ul>
            <li>Développement d'un système de gestion des employés pour une faculté</li>
            <li>Technologies: Java, NetBeans, MySQL</li>
            <li>Gestion complète des données des employés et des départements</li>
          </ul>
        </div>
      </article>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Experience'
}
</script>

<style scoped>
.experience {
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
  background: linear-gradient(180deg, var(--primary), var(--secondary));
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
  border: 3px solid var(--primary);
  border-radius: 50%;
  z-index: 1;
  transition: all var(--transition-base);
}

.timeline-item:hover .timeline-marker {
  background: var(--primary);
  box-shadow: 0 0 0 4px var(--primary-100);
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
  border-color: var(--primary-light);
}

h3 {
  margin: 0 0 0.4rem;
  color: var(--text-primary);
  font-size: 1.1rem;
  font-weight: 600;
}

.period {
  margin: 0 0 0.75rem;
  color: var(--secondary);
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