<template>
  <footer class="main-footer">
    <div class="footer-content">
      <p class="copyright">© {{ currentYear }} Ikbel Bouzouita</p>
      <p class="tagline">IT Architecture & Cloud Computing Student ⚡</p>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  data() {
    return {
      currentYear: new Date().getFullYear()
    }
  }
}
</script>

<style scoped>
.main-footer {
  margin-top: 2rem;
  padding: 1.5rem;
  text-align: center;
  color: var(--text-muted);
  background: var(--white);
  border-top: 1px solid var(--line-light);
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
}

.copyright {
  margin: 0;
  font-size: 0.95rem;
  font-weight: 500;
  color: var(--text-secondary);
}

.tagline {
  margin: 0.35rem 0 0;
  font-size: 0.85rem;
  color: var(--text-muted);
}
</style>