<template>
  <section id="contact" class="contact">
    <h2>📬 Contact</h2>
    <p class="contact-intro">Open to IT architecture, cloud computing roles, and software development opportunities.</p>
    <div class="contact-grid">
      <a href="mailto:Ikbelbouzouita20@gmail.com" class="contact-card">
        <span class="contact-icon">✉️</span>
        <span class="contact-label">Email</span>
        <span class="contact-value">Ikbelbouzouita20@gmail.com</span>
      </a>
      <a href="tel:+21656229549" class="contact-card">
        <span class="contact-icon">📞</span>
        <span class="contact-label">Phone</span>
        <span class="contact-value">+216 56 229 549</span>
      </a>
      <a href="tel:+21650988691" class="contact-card">
        <span class="contact-icon">📱</span>
        <span class="contact-label">Alt Phone</span>
        <span class="contact-value">+216 50 988 691</span>
      </a>
      <a href="https://www.linkedin.com/in/ikbel-bouzouita/" target="_blank" rel="noopener noreferrer" class="contact-card">
        <span class="contact-icon">💼</span>
        <span class="contact-label">LinkedIn</span>
        <span class="contact-value">Connect with me</span>
      </a>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact'
}
</script>

<style scoped>
.contact {
  background: linear-gradient(145deg, var(--white), var(--primary-50));
  text-align: center;
}

h2 {
  margin-top: 0;
  margin-bottom: 0.75rem;
}

.contact-intro {
  color: var(--text-secondary);
  max-width: 500px;
  margin: 0 auto 1.5rem;
}

.contact-grid {
  margin-top: 1rem;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1rem;
}

.contact-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1.5rem 1rem;
  border-radius: var(--radius-lg);
  background: var(--white);
  border: 1px solid var(--line-light);
  text-decoration: none;
  transition: all var(--transition-base);
}

.contact-card:hover {
  transform: translateY(-6px);
  box-shadow: var(--shadow-lg);
  border-color: var(--primary-light);
  text-decoration: none;
}

.contact-icon {
  font-size: 2rem;
  margin-bottom: 0.75rem;
}

.contact-label {
  font-size: 0.8rem;
  font-weight: 600;
  color: var(--text-muted);
  text-transform: uppercase;
  letter-spacing: 0.5px;
  margin-bottom: 0.35rem;
}

.contact-value {
  color: var(--text-primary);
  font-weight: 500;
  font-size: 0.95rem;
}

@media (max-width: 768px) {
  .contact-grid {
    grid-template-columns: 1fr;
  }
  
  .contact-card {
    flex-direction: row;
    gap: 1rem;
    text-align: left;
    padding: 1.25rem;
  }
  
  .contact-icon {
    margin-bottom: 0;
    font-size: 1.5rem;
  }
  
  .contact-card > div {
    flex: 1;
  }
}
</style>