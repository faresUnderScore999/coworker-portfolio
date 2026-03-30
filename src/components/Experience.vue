<template>
  <section id="experience" class="experience">
    <h2>💼 Experience</h2>

    <article class="timeline-item">
      <h3>🚀 Application Web – Gestion des employés (Stage)</h3>
      <p class="period">2024 — Billcom</p>
      <ul>
        <li>Développement d'une application web pour la gestion des employés dans l'entreprise Billcom</li>
        <li>Technologies utilisées: Spring Boot, Angular, MySQL</li>
        <li>Conception et implémentation de fonctionnalités complètes de gestion RH</li>
      </ul>
    </article>

    <article class="timeline-item">
      <h3>🎓 Plateforme Cloud – Gestion des abonnements de services Cloud (Projet de fin d'étude)</h3>
      <p class="period">2024 — ESPRIT</p>
      <ul>
        <li>Développement d'une application web permettant la gestion des abonnements et des services cloud</li>
        <li>Technologies: Node.js, Express.js, React.js, MongoDB</li>
        <li>Architecture cloud moderne avec gestion des utilisateurs et des services</li>
      </ul>
    </article>

    <article class="timeline-item">
      <h3>💻 Application Desktop – Gestion des employés d'un laboratoire d'analyse</h3>
      <p class="period">2023 — Projet Académique</p>
      <ul>
        <li>Conception d'une application desktop permettant la gestion des employés et des données d'un laboratoire</li>
        <li>Technologies: Java, Java Swing, Eclipse, SQL Server</li>
        <li>Interface utilisateur intuitive avec gestion complète des données</li>
      </ul>
    </article>

    <article class="timeline-item">
      <h3>🏢 Application Desktop – Gestion des employés dans une faculté</h3>
      <p class="period">2023 — Projet Académique</p>
      <ul>
        <li>Développement d'un système de gestion des employés pour une faculté</li>
        <li>Technologies: Java, NetBeans, MySQL</li>
        <li>Gestion complète des données des employés et des départements</li>
      </ul>
    </article>
  </section>
</template>

<script>
export default {
  name: 'Experience'
}
</script>

<style scoped>
.experience {
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