<template>
  <section id="contact" class="contact">
    <h2>📬 Contact</h2>
    <p>Open to IT architecture, cloud computing roles, and software development opportunities.</p>
    <div class="contact-grid">
      <a href="mail极速赛车开奖直播历史记录to:Ikbelbouzouita20@gmail.com">✉️ Ikbelbouzouita20@gmail.com</a>
      <a href="tel:+21656229549">📞 +216 56 229 549</a>
      <a href="tel:+21650988691">📞 +216 50 988 691</a>
      <a href="https://www.linkedin.com/in/ikbel-bouzouita/" target="_blank" rel="noopener noreferrer">💼 LinkedIn</a>
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
  background: linear-gradient(145deg, var(--white), var(--bg-1));
  border-radius: 16px;
  padding: 2.2rem 1.4rem;
  text-align: center;
  box-shadow: var(--glow), 0 10px 30px rgba(0, 0, 0, 0.08);
}

h2 {
  margin-top: 0;
}

p {
  color: var(--text-secondary);
}

.contact-grid {
  margin-top: 1rem;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 0.7rem;
}

.contact-grid a {
  display: block;
  padding: 0.75rem 0.8rem;
  border-radius: 10px;
  background: rgba(109, 40, 217, 0.05);
  color: var(--text-secondary);
  text-decoration: none;
  border: 1px solid var(--line);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.contact-grid a:hover {
  transform: translateY(-3px);
  box-shadow: var(--glow), 0 8px 18px rgba(109, 40, 217, 0.1);
  border-color: var(--primary-light);
  background: rgba(109, 40, 217, 0.08);
}
</style>